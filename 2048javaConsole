/*
 * 2048 clone for JAVA console
 *
 * LICENSE
 *
 * pck2048 is a clone of open source game 2048 and released with the GNU General Public License v2.0 (https://www.gnu.org/licenses/gpl-2.0.html).
 * Please see the corresponding license file for details of the license.
 * You are free to use, modify and distribute this software, but all copyright information must remain same.
 *
 * @package    	pkg2048
 * @copyright  	Copyright (c) 2015
 * @version    	1.0
 * @author     	Malik Jahanzaib Sohail <malikjahanzaibsohail@gmail.com>
 */
package pkg2048;


import java.util.*;

public class Main {

    public static void main(String[] args){
        // TODO code application logic here
        int [][]grid = new int[4][4];
        for(int i=0; i<4; i++){
            for(int j=0; j<4; j++){
                grid[i][j] = 0;

            }
        }
        System.out.println("Welcome to 2048!");
        System.out.println("You can enter w for up, s for down, a for left and d for left.");
        System.out.println("Enter n to quit game.");
        grid[1][2]=2;
        grid[0][0]=2;
        render(grid);
        Scanner in = new Scanner(System.in);
        char c = 'y';
        int vacancy;
        
        
        while(c!='n'){
        c = in.next(".").charAt(0);
        
        switch(c){
            case 'w':
                rotateByNinetyToRight(grid);
                add(grid);
                rotateByNinetyToLeft(grid);
                render(grid);
                break;
            case 's':
                rotateByNinetyToLeft(grid);
                add(grid);
                rotateByNinetyToRight(grid);
                render(grid);
                break;
            case 'd':
                add(grid);
                render(grid);
                break;
            case 'a':
                rotateByNinetyToRight(grid);
                rotateByNinetyToRight(grid);
                add(grid);
                rotateByNinetyToLeft(grid);
                rotateByNinetyToLeft(grid);
                render(grid);
                break;
        }
        vacancy = vacancy(grid); 
        if(win(grid)){
                    System.out.println("Yippee! You won the game.");
                    c = 'n';
                }
         
        else if(vacancy==0){
                    System.out.println("Oops! You lost the game.");
                    c = 'n';
                 }
        }
    }
   static void render(int [][]myArray){
       System.out.println("+---+---+---+---+");
       System.out.print("| ");
       gridPrint(myArray[0][0]);
       System.out.print(" | ");
       gridPrint(myArray[0][1]);
       System.out.print(" | ");
       gridPrint(myArray[0][2]);
       System.out.print(" | ");
       gridPrint(myArray[0][3]);
       System.out.println(" |");
       System.out.println("+---+---+---+---+");
       System.out.print("| ");
       gridPrint(myArray[1][0]);
       System.out.print(" | ");
       gridPrint(myArray[1][1]);
       System.out.print(" | ");
       gridPrint(myArray[1][2]);
       System.out.print(" | ");
       gridPrint(myArray[1][3]);
       System.out.println(" |");
       System.out.println("+---+---+---+---+");
       System.out.print("| ");
       gridPrint(myArray[2][0]);
       System.out.print(" | ");
       gridPrint(myArray[2][1]);
       System.out.print(" | ");
       gridPrint(myArray[2][2]);
       System.out.print(" | ");
       gridPrint(myArray[2][3]);
       System.out.println(" |");
       System.out.println("+---+---+---+---+");
       System.out.print("| ");
       gridPrint(myArray[3][0]);
       System.out.print(" | ");
       gridPrint(myArray[3][1]);
       System.out.print(" | ");
       gridPrint(myArray[3][2]);
       System.out.print(" | ");
       gridPrint(myArray[3][3]);
       System.out.println(" |");
       System.out.println("+---+---+---+---+");
    }
static void gridPrint(int x){
    char c;
    if(x==0){
    System.out.print(" ");
    }
    else{
    System.out.print(x);
    }
    }
   public static void cls()
{
    for( int i = 0; i < 25; i++ ) {
        System.out.println("");
    }
    System.out.println("You can enter w for up, s for down, a for left and d for left.");
    System.out.println("Enter n to quit game.");
} 
    public static void add(int [][]grid){
    cls();
    for(int i=3; i>-1; i--){
    
        if((grid[i][3]==grid[i][2])&&grid[i][3]!=0){
            grid[i][3] = grid[i][3] + grid[i][2];
            grid[i][2] = 0;
        }
        if((grid[i][2]==grid[i][1])&&grid[i][2]!=0){
            grid[i][2] = grid[i][2] + grid[i][1];
            grid[i][1] = 0;
        }
        if((grid[i][1]==grid[i][0])&&grid[i][1]!=0){
            grid[i][1] = grid[i][1] + grid[i][0];
            grid[i][0] = 0;
        }
        if((grid[i][0]==grid[i][2])&&(grid[i][2]!=0)&&(grid[i][1]==0)){
            grid[i][2] = grid[i][2] + grid[i][0];
            grid[i][0] = 0;
        }
        if((grid[i][1]==grid[i][3])&&(grid[i][3]!=0)&&(grid[i][2]==0)){
            grid[i][3] = grid[i][2] + grid[i][1];
            grid[i][1] = 0;
        }
        if((grid[i][0]==grid[i][3])&&(grid[i][3]!=0)&&(grid[i][1]==0)&&(grid[i][2]==0)){
            grid[i][3] = grid[i][3] + grid[i][0];
            grid[i][0] = 0;
        }
    }
    shiftRight(grid);
    generate(grid);
    }
     private static void transpose(int[][] m) {
        for (int i = 0; i < m.length; i++) {
            for (int j = i; j < m[0].length; j++) {
                int x = m[i][j];
                m[i][j] = m[j][i];
                m[j][i] = x;
            }
        }
    }
    public static void rotateByNinetyToLeft(int[][] m) {
        transpose(m);
        for (int  i = 0; i < m.length/2; i++) {
            for (int j = 0; j < m[0].length; j++) {
                int x = m[i][j];
                m[i][j] = m[m.length -1 -i][j]; 
                m[m.length -1 -i][j] = x;
            }
        }
    }
      public static void rotateByNinetyToRight(int[][] m) {
        transpose(m);
        for (int  j = 0; j < m[0].length/2; j++) {
            for (int i = 0; i < m.length; i++) {
                int x = m[i][j];
                m[i][j] = m[i][m[0].length -1 -j]; 
                m[i][m[0].length -1 -j] = x;
            }
        }
    }
    public static void shiftRight(int [][]grid){
        for(int i=0; i<4; i++){
            if(grid[i][3]==0){
                if(grid[i][2]==0){
                    if(grid[i][1]==0){
                        if(grid[i][0]!=0){
                            grid[i][3] = grid[i][0];//condition 1
                            grid[i][0] = 0;
                        }
                    }
                    if(grid[i][1]!=0){
                        if(grid[i][0]==0){
                            grid[i][3] = grid[i][1];//condition 2
                            grid[i][1] = 0;
                        }
                        if(grid[i][0]!=0){
                            grid[i][2] = grid[i][1];//condition 3
                            grid[i][1] = grid[i][0];
                            grid[i][0] = 0;
                        }
                    }
                }
                if(grid[i][2]!=0){
                    if(grid[i][1]==0){
                        if(grid[i][0]==0){
                            grid[i][3] = grid[i][2];//condition 4
                            grid[i][2] = 0;
                        }
                        if(grid[i][0]!=0){
                            grid[i][3] = grid[i][2];//condition 5
                            grid[i][2] = grid[i][0];
                            grid[i][0] = 0;
                        }
                    }
                    if(grid[i][1]!=0){
                        if(grid[i][0]==0){
                            grid[i][3] = grid[i][2];//condition 6
                            grid[i][2] = grid[i][1];
                            grid[i][1] = 0;
                        }
                        if(grid[i][0]!=0){
                            grid[i][3] = grid[i][2];//condition 7
                            grid[i][2] = grid[i][1];
                            grid[i][1] = grid[i][0];
                            grid[i][0] = 0;
                        }
                    }
                }
            }
            if(grid[i][3]!=0){
                if(grid[i][2]==0){
                    if(grid[i][1]==0){
                        if(grid[i][0]!=0){
                            grid[i][2] = grid[i][0];//condition 9
                            grid[i][0] = 0;
                        }
                    }
                    if(grid[i][1]!=0){
                        if(grid[i][0]==0){
                            grid[i][2] = grid[i][1];//condition 10
                            grid[i][1] = 0;
                        }
                        if(grid[i][0]!=0){
                            grid[i][2] = grid[i][1];//condition 11
                            grid[i][1] = grid[i][0];
                            grid[i][0] = 0;
                        }
                    }
                }
                if(grid[i][2]!=0){
                    if(grid[i][1]==0){
                        if(grid[i][0]==0){
                            //No need to do anything here at condition 12
                        }
                        if(grid[i][0]!=0){
                            grid[i][1] = grid[i][0];//condition 13
                            grid[i][0] = 0;
                        }
                    }
                    if(grid[i][1]!=0){
                        if(grid[i][0]==0){
                              //No need to do anything here at condition 14
                        }
                        if(grid[i][0]!=0){
                              //No need to do anything here at condition 15
                        }
                    }
                }
            }
        } 
    }
    public static boolean win(int [][]grid){
        boolean win = false;
        for(int i=0; i<4; i++){
            for(int j=0; j<4; j++){
                if(grid[i][j]==2048){
                    win = true;
                }
            }
        }
        return win;
    }
    public static int vacancy(int [][]grid){
        int vacancy = 0;
        for(int i=0; i<4; i++){
            for(int j=0; j<4; j++){
                if(grid[i][j]==0){
                    vacancy++;
                }
            }
        }
        return vacancy;
    }
    public static void generate(int [][]grid){
        boolean check = true;
        int []rnd = new int[2];
        rnd[0] = 2;
        rnd[1] = 4;
        Random randomGenerator = new Random();
        int rint;
        int rint2;
        while(check){
            rint = randomGenerator.nextInt(4);
            if(grid[rint][0]==0){
                grid[rint][0]=rnd[randomGenerator.nextInt(2)];
                check = false;
            }
        }
    }
}
