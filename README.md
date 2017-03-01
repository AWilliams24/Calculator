package Calculator1;

 import java.awt.BorderLayout;
 import java.awt.Color;
 import java.awt.ComponentOrientation;
 import java.awt.Dimension;
 import java.awt.Font;
 import java.awt.GridLayout;
 import java.awt.event.ActionEvent;
 import java.awt.event.ActionListener;
 import java.io.PrintStream;
 import static java.lang.Double.parseDouble;
 import javax.swing.JButton;
 import javax.swing.JFrame;
 import javax.swing.JPanel;
 import javax.swing.JTextField;
 import java.lang.Math;
 import java.util.Stack;
 import javax.swing.SwingConstants;
 import java.math.BigInteger;
 import java.util.Scanner;

public class Calculator1 extends JFrame implements ActionListener {

    double firstDouble;
     //double secondDouble;
     double totalDouble1 = 0.0;
     double totalDouble2 = 0.0;
     char math_operator;
     float Percentage;
     String value="";
     int ctr=0;
     double answer;


    boolean checkFirstdouble = false;
     boolean addPressed = false;
     boolean clearBox = false;
     boolean negative;
    
    
    
   

    private JButton oneButton = new JButton("1");
     private JButton twoButton = new JButton("2");
     private JButton threeButton = new JButton("3");
     private JButton fourButton = new JButton("4");
     private JButton fiveButton = new JButton("5");
     private JButton sixButton = new JButton("6");
     private JButton sevenButton = new JButton("7");
     private JButton eightButton = new JButton("8");
     private JButton nineButton = new JButton("9");
     private JButton zeroButton = new JButton("0");
     private JButton equalsButton = new JButton("=");
     private JButton cButton = new JButton("C");
     private JButton multiplyButton = new JButton("*");
     private JButton divideButton = new JButton("/");
     private JButton addButton = new JButton("+");
     private JButton subtractButton = new JButton("-");
     private JButton dotButton = new JButton(".");
     private JButton piButton = new JButton("π");
     private JButton squaredButton = new JButton("x²");
     private JButton squarerootButton = new JButton("√x");
     private JButton plusMinusButton = new JButton("+/-");
     private JButton factorialButton = new JButton("!");
     private JButton percentageButton = new JButton("%");
     private JButton cubedButton = new JButton("x³");
     private JTextField tbox;
     private JPanel colourPanel;
    
    


    public Calculator1() {
         this.negative = !negative;

        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
         this.setLocation(500,300);
        
         oneButton.addActionListener(this);
         twoButton.addActionListener(this);
         threeButton.addActionListener(this);
         fourButton.addActionListener(this);
         fiveButton.addActionListener(this);
         sixButton.addActionListener(this);
         sevenButton.addActionListener(this);
         eightButton.addActionListener(this);
         nineButton.addActionListener(this);
         zeroButton.addActionListener(this);
         equalsButton.addActionListener(this);
         cButton.addActionListener(this);
         multiplyButton.addActionListener(this);
         divideButton.addActionListener(this);
         addButton.addActionListener(this);
         subtractButton.addActionListener(this);
         dotButton.addActionListener(this);
         piButton.addActionListener(this);
         squaredButton.addActionListener(this);
         squarerootButton.addActionListener(this);
         plusMinusButton.addActionListener(this);
         factorialButton.addActionListener(this);
         percentageButton.addActionListener(this);
         cubedButton.addActionListener(this);


        JPanel jp = new JPanel(new GridLayout(6, 4));
         jp.setPreferredSize(new Dimension(10, 400));

        jp.add(cButton);
         jp.add(squaredButton);
         jp.add(squarerootButton);
         jp.add(piButton);
         jp.add(plusMinusButton);
         jp.add(factorialButton);
         jp.add(percentageButton);
         jp.add(cubedButton);
         jp.add(oneButton);
         jp.add(twoButton);
         jp.add(threeButton);
         jp.add(addButton);
         jp.add(fourButton);
         jp.add(fiveButton);
         jp.add(sixButton);
         jp.add(subtractButton);
         jp.add(sevenButton);
         jp.add(eightButton);
         jp.add(nineButton);
         jp.add(multiplyButton);
         jp.add(zeroButton);
         jp.add(dotButton);
         jp.add(equalsButton);
         jp.add(divideButton);
       

        add(jp, BorderLayout.SOUTH);
         tbox = new JTextField(20);
         tbox.setPreferredSize(new Dimension(40, 50));
        // tbox.setComponentOrientation(ComponentOrientation.RIGHT_TO_LEFT);
         tbox.setHorizontalAlignment(SwingConstants.RIGHT);
         JPanel jpText = new JPanel();
         jpText.add(tbox);
         add(jpText, BorderLayout.NORTH);
         tbox.setEditable(false);
        
         
         colourPanel = new JPanel();
         oneButton.setBackground(Color.PINK);
         twoButton.setBackground(Color.PINK);
         threeButton.setBackground(Color.PINK);
         fourButton.setBackground(Color.PINK);
         fiveButton.setBackground(Color.PINK);
         sixButton.setBackground(Color.PINK);
         sevenButton.setBackground(Color.PINK);
         eightButton.setBackground(Color.PINK);
         nineButton.setBackground(Color.PINK);
         zeroButton.setBackground(Color.PINK);
         dotButton.setBackground(Color.PINK);
         cButton.setBackground(Color.PINK);
         addButton.setBackground(Color.PINK);
         multiplyButton.setBackground(Color.PINK);
         subtractButton.setBackground(Color.PINK);
         divideButton.setBackground(Color.PINK);
         squaredButton.setBackground(Color.PINK);
         squarerootButton.setBackground(Color.PINK);
         piButton.setBackground(Color.PINK);
         equalsButton.setBackground(Color.PINK);
         plusMinusButton.setBackground(Color.PINK);
         factorialButton.setBackground(Color.PINK);
         percentageButton.setBackground(Color.PINK);
         cubedButton.setBackground(Color.PINK);
         tbox.setBackground(Color.lightGray);
        
        
         oneButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         twoButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         threeButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         fourButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         fiveButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         sixButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         sevenButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         eightButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         nineButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         zeroButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         cButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         dotButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         addButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         subtractButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         multiplyButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         divideButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         equalsButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         squaredButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         squarerootButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         piButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         plusMinusButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         factorialButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         percentageButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         cubedButton.setFont(new Font("SerifBold", Font.PLAIN, 30));
         tbox.setFont(new Font("SerifBold", Font.PLAIN, 25));
        
        
        
        
        
                
         pack();
     }

   
    
    
     private void getOperator(String buttonText) {
         math_operator = buttonText.charAt(0);
         totalDouble1 = totalDouble1 + Double.parseDouble(tbox.getText());
         //Math.PI = totalDouble1 + Double.parseDouble(tbox.getText());
         tbox.setText("");
         double variable;
        
       
       /*  switch (math_operator) {
             case '+':
                 totalDouble2 = totalDouble1 + Double.parseDouble(tbox.getText());
                
                 break;
             case '-':
                 totalDouble2 = totalDouble1 - Double.parseDouble(tbox.getText());
                 //totalDouble2 = totalDouble1 - Val(tbox.getText);
                 break;
             case '/':
                 totalDouble2 = totalDouble1 / Double.parseDouble(tbox.getText());
                 break;
             case '*':
                 totalDouble2 = totalDouble1 * Double.parseDouble(tbox.getText());
                 break;
             //case 'π':
                // totalDouble2 = totalDouble1 Math.PI.Double.parseDouble(tbox.getText());
                //break;
             //case
               //'x²':
                //totalDouble2 = totalDouble1 Math.pow.Double.parseDouble(tbox.getText());
                //totalDouble1 = totalDouble2 + Val(tbox.getText);
                // break;
            //case
              // '√x':
               // totalDouble2 = totalDouble1 Math.sqrt.Double.parseDouble(tbox.getText());
              // break;*/
       //  }
     }
        
    
       
  
     @Override
     public void actionPerformed(ActionEvent e) {

     
         if (clearBox == true) {
             tbox.setText("");
             clearBox = false;
            
         }

        if (e.getSource() == oneButton) {
             System.out.println("1");
             tbox.setText(tbox.getText() + "1");
             //System.out.println(firstDouble);
            
         }

        if (e.getSource() == twoButton) {
             System.out.println("2");
             tbox.setText(tbox.getText() + "2");
             //System.out.println(firstDouble);
         }

        if (e.getSource() == threeButton) {
             System.out.println("3");
             tbox.setText(tbox.getText() + "3");
         }
         if (e.getSource() == fourButton) {
             System.out.println("4");
             tbox.setText(tbox.getText() + "4");
         }
         if (e.getSource() == fiveButton) {
             System.out.println("5");
             tbox.setText(tbox.getText() + "5");
         }
         if (e.getSource() == sixButton) {
             System.out.println("6");
             tbox.setText(tbox.getText() + "6");
         }
         if (e.getSource() == sevenButton) {
             System.out.println("7");
             tbox.setText(tbox.getText() + "7");
         }
         if (e.getSource() == eightButton) {
             System.out.println("8");
             tbox.setText(tbox.getText() + "8");
         }
         if (e.getSource() == nineButton) {
             System.out.println("9");
             tbox.setText(tbox.getText() + "9");
         }
         if (e.getSource() == zeroButton) {
             System.out.println("0");
             tbox.setText(tbox.getText() + "0");
         }
         if (e.getSource() == cButton) {
             System.out.println("c");
             tbox.setText(tbox.getText() + "");
             totalDouble2 = 0;
             tbox.setText("");
         }
         if (e.getSource() == factorialButton) {
             System.out.println("!");
             tbox.setText(tbox.getText() + "");
             tbox.setText(""); 
            
         }
         if (e.getSource() == percentageButton) {
             System.out.println("%");
             tbox.setText(tbox.getText() + "");
             tbox.setText("%");
            
         }
         if (e.getSource() == piButton) {
             System.out.println("π");
             tbox.setText(tbox.getText() + "");
             //tbox.setText(Math.PI);
         }
         if (e.getSource() == squarerootButton) {
             System.out.println("√x");
             tbox.setText(tbox.getText() + "");
         }
         if (e.getSource() == squaredButton) {
             System.out.println("x²");
             boolean addButton = true;
                              
         }

        if (e.getSource() == equalsButton) {
             System.out.println("=");
            
             tbox.setText(tbox.getText() + "");
             if (math_operator == '+') {
                 totalDouble2 = totalDouble1 + Double.parseDouble(tbox.getText());
             }
             if (math_operator == '/') {
                 totalDouble2 = totalDouble1 / Double.parseDouble(tbox.getText());
             }
             if (math_operator == '*') {
                 totalDouble2 = totalDouble1 * Double.parseDouble(tbox.getText());
             }
             if (math_operator == '-') {
                 totalDouble2 = totalDouble1 - Double.parseDouble(tbox.getText());
             }
             if (math_operator == '%') {
                totalDouble2 = totalDouble1 % Double.parseDouble(tbox.getText()); 
                ctr=0;
                tbox.setText("" +answer);
                value="";
             }
             //if (math_operator == 'π') {
                 //totalDouble2 = Math.PI.parseDouble(tbox.getText());
           //  }
            // if (math_operator == 'x²') {
           //      totalDouble2 = totalDouble1 Math.POWDouble.parseDouble(tbox.getText());
            // }
            // if (math_operator == '√x') {
            //     totalDouble2 = totalDouble1 Math.sqrtDouble.parseDouble(tbox.getText());
           //  }

            String s1 = Double.toString(totalDouble2);
             tbox.setText(s1);
             totalDouble1 = 0;
             checkFirstdouble = true;
            
            

        }
         if (e.getSource() == addButton) {
             System.out.println(tbox.getText() +  "+");
             Double.parseDouble(tbox.getText());
             String button_text = addButton.getText();
             getOperator(button_text);
            
             //clearBox = true;
             //addPressed = true;
         }
            
             //tbox.setText("+");
             //tbox.setText(tbox.getText() + "+");
            
        
         if (e.getSource() == divideButton) {
             System.out.println(tbox.getText() + "/");
             Double.parseDouble(tbox.getText());
             String button_text = divideButton.getText();
             getOperator(button_text);
             //clearBox = true;
             //addPressed = true;

        }
         if (e.getSource() == multiplyButton) {
             System.out.println(tbox.getText() + "*");
             Double.parseDouble(tbox.getText());
             String button_text = multiplyButton.getText();
             getOperator(button_text);
           
             //addPressed = true;
         }

        if (e.getSource() == subtractButton) {
             System.out.println(tbox.getText() + "-");
             Double.parseDouble(tbox.getText());
             String button_text = subtractButton.getText();
             getOperator(button_text);
           
         }
         if (e.getSource() == piButton) {
             //totalDouble1 = Double.parseDouble(tbox.getText());
             tbox.setText(Double.toString(Math.PI));
             System.out.println(tbox.getText() + "π");
             Double.parseDouble(tbox.getText());
          
             //getOperator(button_text);
             String button_text = piButton.getText();
             double pi = 0.0;
             totalDouble1 = 0;
             checkFirstdouble = true;
            
            
         }
         if (e.getSource() == squaredButton) {
             totalDouble1 = Double.parseDouble(tbox.getText());
             tbox.setText(Double.toString(totalDouble1*totalDouble1));
             System.out.println(tbox.getText() + "x²");
             Double.parseDouble(tbox.getText());
             String button_text = squaredButton.getText();
             totalDouble1 = 0;
             checkFirstdouble = true;
             //getOperator(button_text);
            
           
         }
         if (e.getSource() == squarerootButton) {
             totalDouble1 = Double.parseDouble(tbox.getText());
             tbox.setText(Double.toString(java.lang.Math.sqrt(totalDouble1)));
             System.out.println(tbox.getText() + "√x");
             //getOperator(button_text);
             Double.parseDouble(tbox.getText());
             String button_text = squarerootButton.getText();
             //clearBox = true;
             totalDouble1 = 0;
             checkFirstdouble = true;
           
         }
         if (e.getSource() == dotButton) {
             System.out.println(".");
             Double.parseDouble(tbox.getText());
             tbox.setText(tbox.getText() + ".");
             clearBox = false;
             addPressed = true;
         }  
          if (e.getSource() == cubedButton) {
             totalDouble1 = Double.parseDouble(tbox.getText());
             tbox.setText(Double.toString(totalDouble1*totalDouble1*totalDouble1));
             System.out.println(tbox.getText() + "x³");
             Double.parseDouble(tbox.getText());
             String button_text = cubedButton.getText();
             totalDouble1 = 0;
             checkFirstdouble = true;
             //getOperator(button_text);
           
           
          }
           if (e.getSource() == plusMinusButton) {
             System.out.println("+/-");
             totalDouble1 = Double.parseDouble(tbox.getText());
             totalDouble1 *= -1;
             tbox.setText(Double.toString(totalDouble1));
             totalDouble1 = 0;
             checkFirstdouble = true;
           } 
           if (e.getSource() == factorialButton) {
             Scanner input = new Scanner(System.in);
                 //int factor = 1;
                 //int number = 0;
               //for (int i=1; i<=number; i++){
                 //return factor;
           }
            if (e.getSource() == percentageButton) {
             totalDouble1 = Double.parseDouble(tbox.getText());
             ctr = 0;
             value = "";
             answer = (totalDouble1/100);
             tbox.setText("" + answer);
             
             
            }
     
     }
     


          
    
    
     public static void main(String args[]) throws Exception {
         new Calculator1().setVisible(true);
      }}


    
         
         
