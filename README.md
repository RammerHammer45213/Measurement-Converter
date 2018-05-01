
import java.text.DecimalFormat;

/*
 * RaCoc9605
 * ICS3U
 * This program is a GUI-based program that converts multiple measurements.
 */

/**
 *
 * @author RaCoc9605
 */
public class measurementConverter extends javax.swing.JFrame {

    /**
     * Creates new form measurementConverter
     */
    public measurementConverter() {
        initComponents();
    }

    /**
     * This method is called from within the constructor to initialize the form.
     * WARNING: Do NOT modify this code. The content of this method is always
     * regenerated by the Form Editor.
     */
    @SuppressWarnings("unchecked")
    // <editor-fold defaultstate="collapsed" desc="Generated Code">                          
    private void initComponents() {

        title = new javax.swing.JLabel();
        measurementSystem = new javax.swing.JLabel();
        explain = new javax.swing.JLabel();
        measurement = new javax.swing.JLabel();
        convertedOutput = new javax.swing.JLabel();
        conversionInput = new javax.swing.JTextField();
        measureInput = new javax.swing.JTextField();
        measureButton = new javax.swing.JButton();
        jLabel1 = new javax.swing.JLabel();

        setDefaultCloseOperation(javax.swing.WindowConstants.EXIT_ON_CLOSE);

        title.setFont(new java.awt.Font("Tahoma", 0, 36)); // NOI18N
        title.setText("Measurement Converter");

        measurementSystem.setFont(new java.awt.Font("Tahoma", 0, 16)); // NOI18N
        measurementSystem.setText("Enter Which Conversion to Use:");

        explain.setFont(new java.awt.Font("Tahoma", 0, 12)); // NOI18N
        explain.setText("In to Cm (1), Ft to Cm (2), Yrd to M (3) Miles to Km (4)");

        measurement.setFont(new java.awt.Font("Tahoma", 0, 16)); // NOI18N
        measurement.setText("Enter Your Measurement in the Conversion Chosen:");

        convertedOutput.setFont(new java.awt.Font("Tahoma", 0, 16)); // NOI18N
        convertedOutput.setText("Your converted measurement will display here!");

        conversionInput.setFont(new java.awt.Font("Tahoma", 0, 16)); // NOI18N

        measureInput.setFont(new java.awt.Font("Tahoma", 0, 16)); // NOI18N

        measureButton.setFont(new java.awt.Font("Tahoma", 0, 16)); // NOI18N
        measureButton.setText("Measure!");
        measureButton.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                measureButtonActionPerformed(evt);
            }
        });

        jLabel1.setFont(new java.awt.Font("Tahoma", 0, 12)); // NOI18N
        jLabel1.setText("Cm to In (5), Cm to Ft (6), M to Yrd (7), Km to Miles (8)");

        javax.swing.GroupLayout layout = new javax.swing.GroupLayout(getContentPane());
        getContentPane().setLayout(layout);
        layout.setHorizontalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(layout.createSequentialGroup()
                        .addGap(33, 33, 33)
                        .addComponent(title))
                    .addGroup(layout.createSequentialGroup()
                        .addContainerGap()
                        .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                            .addComponent(measurement)
                            .addComponent(explain)
                            .addGroup(layout.createSequentialGroup()
                                .addComponent(measurementSystem)
                                .addGap(18, 18, 18)
                                .addComponent(conversionInput, javax.swing.GroupLayout.PREFERRED_SIZE, 95, javax.swing.GroupLayout.PREFERRED_SIZE))
                            .addComponent(jLabel1))
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)
                        .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING, false)
                            .addComponent(measureButton, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                            .addComponent(measureInput))))
                .addContainerGap(javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE))
            .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, layout.createSequentialGroup()
                .addGap(0, 0, Short.MAX_VALUE)
                .addComponent(convertedOutput)
                .addGap(81, 81, 81))
        );
        layout.setVerticalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addGap(24, 24, 24)
                .addComponent(title)
                .addGap(46, 46, 46)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(measurementSystem)
                    .addComponent(conversionInput, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING, false)
                    .addComponent(measureButton)
                    .addGroup(layout.createSequentialGroup()
                        .addComponent(explain)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                        .addComponent(jLabel1)))
                .addGap(21, 21, 21)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(measurement)
                    .addComponent(measureInput, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, 11, Short.MAX_VALUE)
                .addComponent(convertedOutput)
                .addGap(21, 21, 21))
        );

        pack();
    }// </editor-fold>                        

    private void measureButtonActionPerformed(java.awt.event.ActionEvent evt) {
    /**
    *These are the variables used in the program to find the conversion wanted and the measurement that has been put into the GUI.
    */
        double conversion = Double.parseDouble (conversionInput.getText());
        double measurement = Double.parseDouble (measureInput.getText());
        double convert = 0.0;
        
        /**
        *This formats the outputted measurements to be displayed at a maximum of two decimal places.
        */
        DecimalFormat x = new DecimalFormat ("##.##");
        
        /**
        *These if statements do the conversion and display them onto a label on the GUI.
        */
        if (conversion == 1)
        {
            convert = measurement * 2.54;
            convertedOutput.setText("" + measurement + " inches is equal to " + (x.format(convert)) + " centimetres.");
        }
        else if (conversion == 2)
        {
            convert = measurement * 30.48;
            convertedOutput.setText("" + measurement + " feet is equal to " + (x.format(convert)) + " centimetres.");
        }
        else if (conversion ==3)
        {
            convert = measurement * 0.91;
            convertedOutput.setText("" + measurement + " yards is equal to " + (x.format(convert)) + " metres.");
        }
        else if (conversion == 4)
        {
            convert = measurement * 1.6;
            convertedOutput.setText("" + measurement + " miles is equal to " + (x.format(convert)) + " kilometres.");
        }
        else if (conversion ==5)
        {
            convert = measurement / 2.54;
            convertedOutput.setText("" + measurement + " centimetres is equal to " + (x.format(convert)) + " inches.");
        }
        else if (conversion ==6)
        {
            convert = measurement / 30.48;
            convertedOutput.setText("" + measurement + " centimetres is equal to " + (x.format(convert)) + " feet.");
        }
        else if (conversion ==7)
        {
            convert = measurement / 0.914;
            convertedOutput.setText("" + measurement + " metres is equal to " + (x.format(convert)) + " yards.");
        }
        else 
        {
            convert = measurement / 1.61;
            convertedOutput.setText("" + measurement + " kilometres is equal to " + (x.format(convert)) + " miles.");
        }
    }                                             

    /**
     * @param args the command line arguments
     */
    public static void main(String args[]) {
        /* Set the Nimbus look and feel */
        //<editor-fold defaultstate="collapsed" desc=" Look and feel setting code (optional) ">
        /* If Nimbus (introduced in Java SE 6) is not available, stay with the default look and feel.
         * For details see http://download.oracle.com/javase/tutorial/uiswing/lookandfeel/plaf.html 
         */
        try {
            for (javax.swing.UIManager.LookAndFeelInfo info : javax.swing.UIManager.getInstalledLookAndFeels()) {
                if ("Nimbus".equals(info.getName())) {
                    javax.swing.UIManager.setLookAndFeel(info.getClassName());
                    break;
                }
            }
        } catch (ClassNotFoundException ex) {
            java.util.logging.Logger.getLogger(measurementConverter.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (InstantiationException ex) {
            java.util.logging.Logger.getLogger(measurementConverter.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (IllegalAccessException ex) {
            java.util.logging.Logger.getLogger(measurementConverter.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (javax.swing.UnsupportedLookAndFeelException ex) {
            java.util.logging.Logger.getLogger(measurementConverter.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        }
        //</editor-fold>

        /* Create and display the form */
        java.awt.EventQueue.invokeLater(new Runnable() {
            public void run() {
                new measurementConverter().setVisible(true);
            }
        });
    }

    // Variables declaration - do not modify                     
    private javax.swing.JTextField conversionInput;
    private javax.swing.JLabel convertedOutput;
    private javax.swing.JLabel explain;
    private javax.swing.JLabel jLabel1;
    private javax.swing.JButton measureButton;
    private javax.swing.JTextField measureInput;
    private javax.swing.JLabel measurement;
    private javax.swing.JLabel measurementSystem;
    private javax.swing.JLabel title;
    // End of variables declaration                   
}
