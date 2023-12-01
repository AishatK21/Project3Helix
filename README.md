# Project3Helix
import java.awt.Color;
import java.util.Scanner;
import java.awt.Graphics;
import java.util.Random; 
//Normal Credit
public class Helix{
  
  public static Scanner input; //Scanner decalred across all scopes
  
   public static void main(String[] args){
    input = new Scanner(System.in); //initalized 
    
    System.out.println("UTSA - Fall 2023 - CS1083 - Section 006 - Prj 3 - Helix - written by Aishat Kolawole");
    
    System.out.println("Please, input the speed (1 - 10)");
    int speed = input.nextInt();
    
    System.out.println("Please, input the number of times the line will be shown: ");
    int numTimes = input.nextInt();
    
    System.out.println("Please, input the number corresponding to the color you want to show to helix ");
    System.out.println("0 - Green, 1 - Gray, 2 - Yellow, 3 - Red, 4 - Orange, 5 - Pink, 6 - Dark gray, 7 - Blue, and 8 - Black: "); 
    int color = input.nextInt();
    
    int[] coordinates = {100,100,300,300};
     //An integer variable to determine if the start coordinate of the line last movement is right, down, left, or upv
    int lineMovement = 0;
   
     
    drawHelix(speed, numTimes, color, lineMovement, coordinates);
   }
   
   public static void drawHelix(int speed, int numTimes, int color, int lineMovement, int[] coordinates){
     DrawingPanel panel = new DrawingPanel(400, 400); 
     Graphics g = panel.getGraphics(); //graphics object
     
     panel.setBackground(Color.BLACK);
     
     //variables
     
     g.setColor(Color.WHITE);
     
     g.fillRect(100, 100, 200, 200);
  
     g.drawString("UTSA - Fall 2023 - CS1083 - Section 006 - Prj 3 - Helix - Aishat Kolawole", 5, 60);
    
     int i;
     for(i = 0; i <= numTimes; i++){
       g.clearRect(0, 300, 400, 100); //clear each time
       g.drawString("Speed: " + speed, 160, 90);
       g.drawString("i: " + i, 200,350);
       g.drawString("("+coordinates[0]+","+coordinates[1]+")"+","+"("+coordinates[2]+","+coordinates[3]+")", 160, 375);
       
       if(i == numTimes){
         break;
       }
       g.setColor(getColor(color));
       
       g.drawLine(coordinates[0], coordinates[1], coordinates[2], coordinates[3]); 
 
     
       panel.sleep(100 / speed); 
       
       g.setColor(Color.WHITE);
       g.drawLine(coordinates[0], coordinates[1], coordinates[2], coordinates[3]);
       
       if(coordinates [0] == 300 && coordinates[1] == 100){
            lineMovement = 1; //move down
       }else if(coordinates[0] == 300 && coordinates[1] == 300){
            lineMovement = 2; //move left
       }else if(coordinates[0] == 100 && coordinates[1] == 300){
            lineMovement = 3; //move up
       }else if(coordinates[0] == 100 && coordinates[1] == 100){
            lineMovement = 0; //move right 
       }
      
      System.out.print("("+coordinates[0]+","+coordinates[1]+")"+","+"("+coordinates[2]+","+coordinates[3]+")" + "\n");
      
      boolean isClockwise = true;
      newPos(isClockwise, coordinates, lineMovement); //updated coordinates
     }
     g.setColor(getColor(color));
     g.drawLine(coordinates[0], coordinates[1], coordinates[2], coordinates[3]);
   }

      public static Color getColor(int color) { 
        switch (color) { 
            case 0: 
                return Color.GREEN; 
            case 1: 
                return Color.GRAY; 
            case 2: 
                return Color.YELLOW; 
            case 3: 
                return Color.RED; 
            case 4: 
                return Color.ORANGE; 
            case 5: 
                return Color.PINK; 
            case 6: 
                return Color.DARK_GRAY; 
            case 7: 
                return Color.BLUE; 
            case 8: 
                return Color.BLACK; 
            default: 
                return Color.WHITE; 
        } 
    }
      public static void newPos(boolean isClockwise,int[] coordinates, int lineMovement){
       
       if(lineMovement == 0){
          coordinates[0] +=10; //moves X1 right
          coordinates[2] -=10; //moves x2 left
       }else if(lineMovement == 1){
          coordinates[1] +=10; //moves y1 down
          coordinates[3] -=10; //moves y2 up
       }else if(lineMovement == 2){
          coordinates[0] -=10; //moves X1 left
          coordinates[2] +=10; //moves x2 right
       }else if(lineMovement == 3){
          coordinates[1] -=10; //moves y1 up
          coordinates[3] +=10; //moves y2 down
       }   
   } 
}
