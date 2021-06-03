class game ():
  def __init(self):
    self.floor = [[" ", " ", " "],[" ", " ", " "],[" ", " ", " "]]
    self.status = True
    self.move = 0

  def play(self):
    if self.move  % 2== 0:
      self.player1()
      
    else:
      self.player2()

    self.status=self.control()

    if not self.status:
       self.floorspace()
       Winner = ""
       if self.status % 2 == 0:
         Winner = "X"
       else:
         Winner = "O"  

       print("Game Over. Winner is: ".format(winner) )

    self.move += 1  

  def player1(self):
      self.floorspace()
      print("First Player...")
      line = int(input("Enter line: "))
      while line <1 or line >3:
        line= int(input("The value to be entered can be up to 3.Please try again:"))

      column = int(input ("Enter column: "))
      while column <1 or line >3:
        column = int(input("The value to be entered can be up to 3.Please try again:"))

      if self.full(line,column):
        self.player1()
      else:
        self.floor[line-1][column-1] = "X"  

  def player2(self):
      self.floorspace()
      print("Second Player...")
      line = int(input("Enter line: "))
      while line <1 or line >3:
        line= int(input("The value to be entered can be up to 3.Please try again:"))

      column = int(input ("Enter column: "))
      while column <1 or line >3:
        column = int(input("The value to be entered can be up to 3.Please try again:"))

      if self.full(line,column):
        self.player2()
      else:
        self.floor[line -1][column -1] = "O"     


  def full(self, line, column):
    if self.floor[line-1][column-1] != " ":
        return True
    else:
        return False  
      

  def floorspace(self):  
      for a in self.floor:
        print(a)  


  def control(self):
   #yatay
    if [self.floor[0][0],self.floor[0][1],self.floor[0][2]]==["X","X","X"] or [self.floor[0][0],self.floor[0][1],self.floor[0][2]]==["O","O","O"]:
        return False
    if [self.floor[1][0], self.floor[1][1], self.floor[1][2]]==["X","X","X"] or [self.floor[1][0], self.floor[1][1], self.floor[1][2]]==["O","O","O"]:
        return False     
    if [self.floor[2][0], self.floor[2][1], self.floor[2][2]]==["X","X","X"] or [self.floor[2][0], self.floor[2][1], self.floor[2][2] ]==["O","O","O"]:
        return False

      #dikey
    if [self.floor[0][0], self.floor[1][0], self.floor[2][0]    ]==["X","X","X"] or [self.floor[0][0], self.floor[0][0], self.floor[0][0]    ]==["O","O","O"]:
        return False
    if [self.floor[0][1], self.floor[1][1], self.floor[2][1]    ]==["X","X","X"] or [self.floor[0][1], self.floor[0][1], self.floor[0][1]    ]==["O","O","O"]:
        return False     
    if [self.floor[0][2], self.floor[1][2], self.floor[2][2]    ]==["X","X","X"] or [self.floor[0][2], self.floor[0][2], self.floor[0][2]    ]==["O","O","O"]:
        return False

      #çapraz
    if [self.floor[0][0], self.floor[1][1], self.floor[2][2]    ]==["X","X","X"] or [self.floor[0][0], self.floor[1][1], self.floor[2][2]    ]==["O","O","O"]:
        return False
    if [self.floor[0][0], self.floor[1][1], self.floor[2][2]    ]==["X","X","X"] or [self.floor[0][0], self.floor[1][1], self.floor[2][2]    ]==["O","O","O"]:
        return False     

    return True  
   
    


    game= Game()

    while game.status:
          play.game()
