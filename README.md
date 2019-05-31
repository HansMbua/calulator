# calulator
import java.awt.GridLayout;
import java.awt.BorderLayout;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.Container;
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.JButton;
import javax.swing.JTextField;

public class Calculator extends JFrame implements ActionListener {
    private JButton[] buttons, button2;
    private Container container;
    private JPanel buttonJPanel, textPane;
    private GridLayout gridLayout1, gridLayout2;
    private String[] numbers = {"7","8","9","/","4","5","6","*","1","2","3","-","0",".","+","="};
    private JTextField textField;
    public Calculator(){
    
        super(" Calculator ");
       textField = new JTextField(20);
       
       textField.setEditable(true);
     
       buttons = new JButton[numbers.length];
       buttonJPanel = new JPanel();
       buttonJPanel.setLayout(new GridLayout(4,4,5,10));
      
       
        for(int count = 0; count < numbers.length; count++)
        {
        buttons[ count ] = new JButton( numbers[ count ] );// initilizing array 
        buttons[ count ].addActionListener(this);
         buttonJPanel.add(buttons[ count ]);// collects the buttons and put them in a layout of (4,4)
        }// end for
        
        container = getContentPane();
        container.add(textField , BorderLayout.NORTH);
        container.add(buttonJPanel, BorderLayout.CENTER);

      
        
    }// end contructor
    
    
    @Override
    public void actionPerformed(ActionEvent event)
    {
    
    for(JButton button : buttons )
    {
    
         if( event.getSource() == button )
             textField.setText( buttons.toString());
         
    }
    }// end actionPerormed 
    
}// end of class calculator
