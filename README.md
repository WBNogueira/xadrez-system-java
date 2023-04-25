# Jogo de xadrez com Java

##### Primeira classe: Position (posição tabuleiro)

Tópicos:

- Encapsulamento

- Construtores

- ToString (Object / overrinding)

##### Começando a implementar Board e Piece

- Classes: Piece, Board [public]

- Tópicos:
  
  - Associações
  
  - Modificadores de encapsulamento e acessos
  
  - Estrutura de dados - tópicos:
    
    - Matriz.

##### Camada de xadrez e impressão do tabuleiro

   a  b  c  d  e  f  g  h
8  -  -   -   -   -  -   -   -
7  -  -   -   -   -  -   -   -
6  -  -   -   -   -  -   -   -
5  -  -   -   -   -  -   -   -
4  -  -   -   -   -  -   -   -
3  -  -   -   -   -  -   -   -
2  -  -   -   -   -  -   -   -
1  -  -   -   -   -  -   -   -
  a  b  c  d   e  f  g  h

###### Lista de controle:

- Métodos: Board.Piece (linha, coluna) e Board.Piece (posição)
- Enun Chess.Color
- Classe Chess.ChessPiece [public]
- Classe Chess.ChessMatch [public]
- Classe ChessConsole.UI
- POO tópicios:
  - Enumerações
  - Modificadores de encapsulamento/acesso
  - Herança
  - Downcasting
  - Membros estáticos
  - Padrão de camadas
- Estruturas de dados - tópicos:
  - Matriz

##### Colocando as peças no tabuleiro

###### Lista de controle:

- Método: Board.PlacePiece (peça, posição)
- Classes: Rook, King [public]
- Método: ChessMatch.InitialSetup
- POO tópicos:
  - Herança
  - Substituindo (Overrriding)
  - Poliformismo (ToString)

##### BoardException e programação defensiva

###### Lista de controle:

- Classe BoardException [public]
- Métodos:  Board.PositionExists, Board.ThereIsAPiece
- Implementar programação defensiva em métodos do tabuleiro
- POO tópicos:
  - Exceções (Exceptions)
  - Construtores (uma string deve ser informada para a exceção)

##### ChessException e ChessPosition

###### Lista de controle:

- Classe ChessException [public]
- Classe ChessPosition [public]
- Refatorar ChessMatch.InitialSetup
- POO tópicos:
  - Exceções (Exceptions)
  - Encapsulamento
  - Construtores (uma string deve ser informada para a exceção)
  - Substituindo (Overrriding)
  - Membros estáticos
  - Padrão de camadas

##### Melhoria na impressão do tabuleiro

###### Cor no terminal:

- Windows: Git Bash
- Mac: Google "osx terminal color"

###### Lista de controle:

- Colocar mais peças no tabuleiro
- Distinguir as cores das peças no método UI.PrintPiece

##### Movendo as peças

###### Lista de controle:

- Método Board.RemovePiece
- Método UI.ReadChessPosition
- Método ChessMatch.PerformChessMove
  - Método ChessMatch.MakeMove
  - Método ChessMatch.ValidadeSourcePosition
- Escrever a lógica básica em Program.cs
- POO tópicos:
  - Exceções
  - Encapsulamento

##### Manipulando exceções e limpando a tela

###### Limpar tela usando Java:

// https://stackoverflow.com/questions/2979383/java-clear-the-console
public static void clearScreen() {
     System.out.print("\033[H\033[2J");
     System.out.flush();
}

###### Lista de controle:

- ChessException
- InputMismatchException

##### Possíveis movimentos de uma peça

###### Lista de controle:

- Métodos das peças:
  - PossibleMoves [abstract]
  - PossibleMove
  - IsThereAnyPossibleMove
- Implementação básica do PossibleMove para Torre e Rei (Rook e King)
- Atualizar ChessMatch.ValidadeSourcePosition
- POO tópicos:
  - Método abstrato / classe
  - Exceções

##### Implementando possíveis movimentos da Torre (Rook)

###### Lista de controle:

- Método ChessPiece.IsThereOpponentPiece(position) [protected]
- Implemento Rook.PossibleMoves
- Método ChessMatch.ValidateTargetPosition
- POO tópicos:
  - Polimorfismo
  - Modificadores de encapsulamento/acesso [protected]
  - Exceções

##### Imprimindo movimentos possíveis

###### Lista de controle:

- Método ChessMatch.PossibleMoves
- Método d UI.PrintBoard [overload]
- Refatorar a lógica do programa principal
- POO tópico:
  - Sobrecarga (Overloading)

##### Implementando possíveis movimentos de Rei (King)

###### Lista de controle:

- Método King.CanMove(position) [private]

- Implemento King.PossibleMoves

- POO tópicos:
  
  - Encapsulamento
  - Polimorfismo

##### Trocar de jogador a cada turno

###### Lista de controle:

- Classe ChessMatch
- Propriedades Turn, CurrentPlayer [private set]
- Método NextTurn [private]
- Atualizar PerformChessMove
- Atualizar ValidadeSourcePosition
- Método d UI.PrintMatch
- POO tópicos:
  - Encapsulamento
  - Exceções

##### Manuseio de peças capturadas

###### Lista de controle:

- Método UI.PrintCapturedPieces
- Atualizar e UI.PrintMatch
- Atualizar a lógica da classe Program
- Listas no ChessMatch:  _piecesOnTheBoard, _capturedPieces
  - Atualizar construtor
  - Atualizar PlaceNewPiece
  - Atualizar MakeMove
  - POO tópicos:
  - Encapsulamento
  - Construtores
  - Estruturas de dados tópicos:
  - Lista

##### Verificar a lógica

###### Regras

- Xeque significa que seu rei está sob ameaça de pelo menos uma peça do oponente
- Você não pode se colocar em cheque

###### Lista de controle:

- Propriedade ChessPiece.ChessPosition [get]
- Classe ChessMatch:
  - Método UndoMove
  - Propriedade Check [private set]
  - Método Opponent [private]
  - Método King (color) [private]
  - Método TestCheck
  - Atualizar PerformChessMove
- Atualizar UI.PrintMatch

##### Lógica do xeque-mate

###### Lista de controle:

- Classe ChessMatch:
  - Propriedade  Checkmate [private set]
  - Método TestCheckmate [private]
  - Atualizar e PerformChessMove
- Atualizar UI.PrintMatch
- Atualizar a lógica da classe Program

##### Contagem de movimentos das peças

###### Lista de controle:

- Classe ChessPiece:
  - Propriedade MoveCount [private set]
  - Método IncreaseMoveCount [internal]
  - Método DecreaseMoveCount [internal]
- Classe ChessMatch:
  - Atualizar MakeMove
  - Atualizar UndoMove
- POO tópicos:
  - Encapsulamento

##### Peão (Pawn)

###### Lista de controle:

- Classe Pawn
- Atualizar ChessMatch.InitialSetup
- POO tópicos:
  - Encapsulamento
  - Herança
  - Polimorfismo

##### Bispo (Bishop)

###### Lista de controle:

- Classe Bishop
- Atualizar ChessMatch.InitialSetup
- POO tópicos:
  - Encapsulamento
  - Herança
  - Polimorfismo

##### Cavalo (Knight)

###### Lista de controle:

- Classe Knight
- Atualizar ChessMatch.InitialSetup
- POO tópicos:
  - Encapsulamento
  - Herança
  - Polimorfismo

##### Rainha (Queen)

###### Lista de controle:

- Classe Queen
- Atualizar ChessMatch.InitialSetup
- POO tópicos:
  - Encapsulamento
  - Herança
  - Polimorfismo

##### Movimento especial - Roque

###### Lista de controle:

- Atualizar King
- Atualizar ChessMatch.MakeMove
- Atualizar ChessMatch.UndoMove

##### Movimento especial - En Passant

###### Lista de controle:

- Registre um peão que pode ser capturado por en passant no próximo turno
  - Propriedade ChessMatch.EnPassantVulnerable
  - Atualizar ChessMatch.PerformChessMove
- Atualizar Pawn.PossibleMoves
- Atualizar ChessMatch.MakeMove
- Atualiar ChessMatch.UndoMove
- Atualizar ChessMatch.InitialSetup

##### Movimento especial - Promoção

###### Lista de controle:

- Propriedade ChessMatch.Promoted
- Atualizar ChessMatch.PerformChessMove
- Método ChessMatch.ReplacePromotedPiece
- Atualizar a lógica da classe Program



###### Fonte: Curso Java Completo 2023 Udemy - Professor Nelio Alves
