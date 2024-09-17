# Project3Helix

//Call drawHelix() to start the operations of this program 
    
    //set background black and white centered box
    //Color black = new Color(0, 0, 0);
    //panel.setBackground(black);
    //g.setColor(Color.White);
    //g.fillRect(0,0,0,0);
    
    //show specifics?
    System.out.println("Please, input the speed (1 - 10");
    System.out.println("Please, input the number of times the line will be shown: ");
        //userinput
    System.out.println("Please, input the number corresponding to the color you want to show to helix ");
    System.out.println("0 - Green, 1 - Gray, 2 - Yellow, 3 - Red, 4 - Orange, 5 - Pink, 6 - Dark gray, 7 - Blue, and 8 - Black: ");
    
    //show speed
    //Last move? --> if yes exit program
    //if no getColor() method
      
  }
  public static void drawHelix(){
    DrawingPanel panel = new DrawingPanel(400, 400);
    Graphics g = panel.getGraphics();
    
    /*A Scanner variable to obtain information from the keyboard
       An integer variable to store the numeric value corresponding to the color
     //int colCode; 0 - 8 
       An integer variable to store the speed that the helix will move
     int speed;
       A boolean variable to store if the user wants the helix to move clockwise or not
     boolean Clockwise = scnr.nextBoolean();
     
       An array of 4 integers which will correspond to the start and end coordinates of the line to draw
     
       An integer variable to determine if the start coordinate of the line last movement is right, down, left, or up
     // int dir; direction or movement
       Other variables needed for the system to work (loop variables, etc.)
