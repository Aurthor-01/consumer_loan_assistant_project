package consumer_loan_assistant_project;

import java.awt.Color;
import java.text.DecimalFormat;
import javax.swing.JOptionPane;
import javax.swing.JTextField;

public class Main_Frame extends javax.swing.JFrame {

    boolean computePayment;
    int newNumber;

    void newLoanCkicked() {
        if (computePayment) {
            paymentTextField.setText("");
        } else {
            monthsTextField.setText("");
        }
        analysisTextArea.setText("");
        computeButton.setEnabled(true);
        newLoanButton.setEnabled(false);
        balanceTextField.requestFocus();

    }

    private void computeButtonActionPerformed() {
        double balance, interest, payment;
        int months;
        double monthlyInterest, multiplier;
        double loanBalance, finalPayment;
        if (validateDecimalNumber(balanceTextField)) {
            balance
                    = Double.valueOf(balanceTextField.getText()).doubleValue();
        } else {
            JOptionPane.showConfirmDialog(null, "Invalid or empty Loan Balance entry.\nPleasecorrect.", "Balance Input Error", JOptionPane.DEFAULT_OPTION, JOptionPane.INFORMATION_MESSAGE);
            return;
        }
        if (validateDecimalNumber(interestTextField)) {
            interest
                    = Double.parseDouble(interestTextField.getText());

        } else {
            JOptionPane.showConfirmDialog(null, "Invalid or empty Interest Rate entry.\nPleasecorrect.", "Interest Input Error", JOptionPane.DEFAULT_OPTION, JOptionPane.INFORMATION_MESSAGE);
            return;
        }
        monthlyInterest = interest / 1200;
        if (computePayment) {

            if (validateDecimalNumber(monthsTextField)) {
                months
                        = Integer.parseInt(monthsTextField.getText());
            } else {
                JOptionPane.showConfirmDialog(null, "Invalid or empty Number of Paymentsentry.\nPlease correct.", "Number of Payments Input Error", JOptionPane.DEFAULT_OPTION, JOptionPane.INFORMATION_MESSAGE);
                return;
            }
            if (interest == 0) {
                payment = balance / months;
            } else {
                multiplier = Math.pow(1 + monthlyInterest, months);
                payment = balance * monthlyInterest * multiplier / (multiplier - 1);
            }
            paymentTextField.setText(new DecimalFormat("0.00").format(payment));
        } else {
        }
        {
            if (validateDecimalNumber(paymentTextField)) {
                payment
                        = Double.parseDouble(paymentTextField.getText());
                if (payment <= (balance * monthlyInterest + 1.0)) {
                    if (JOptionPane.showConfirmDialog(null, "Minimum payment must be $" + new DecimalFormat("0.00").format((int) (balance * monthlyInterest + 1.0)) + "\n" + "Do you want to use the minimum payment?", "Input Error", JOptionPane.YES_NO_OPTION, JOptionPane.QUESTION_MESSAGE) == JOptionPane.YES_OPTION) {
                        paymentTextField.setText(new DecimalFormat("0.00").format((int) (balance
                                * monthlyInterest + 1.0)));
                        payment = Double.parseDouble(paymentTextField.getText());
                    } else {
                        paymentTextField.requestFocus();
                        return;
                    }
                }
            } else {
                JOptionPane.showConfirmDialog(null, "Invalid or empty Monthly Paymententry.\nPlease correct.", "Payment Input Error", JOptionPane.DEFAULT_OPTION, JOptionPane.INFORMATION_MESSAGE);
                return;
            }
            if (interest == 0) {
                months = (int) (balance / payment);
            } else {
            }
            {
                months = (int) ((Math.log(payment) - Math.log(payment - balance * monthlyInterest))
                        / Math.log(1 + monthlyInterest));
            }
            monthsTextField.setText(String.valueOf(months));
        }
        payment
                = Double.parseDouble(paymentTextField.getText());
        analysisTextArea.setText("Loan Balance: $" + new DecimalFormat("0.00").format(balance));
        analysisTextArea.append("\n" + "Interest Rate: " + new DecimalFormat("0.00").format(interest) + "%");
        loanBalance = balance;
        for (int paymentNumber = 1; paymentNumber <= months - 1; paymentNumber++) {
            loanBalance += loanBalance * monthlyInterest - payment;
        }
        finalPayment = loanBalance;
        if (finalPayment > payment) {
            loanBalance += loanBalance * monthlyInterest - payment;
            finalPayment = loanBalance;
            months++;
            monthsTextField.setText(String.valueOf(months));
        }
        analysisTextArea.append("\n\n" + String.valueOf(months - 1) + " Payments of $" + new DecimalFormat("0.00").format(payment));
        analysisTextArea.append("\n" + "Final Payment of: $" + new DecimalFormat("0.00").format(finalPayment));
        analysisTextArea.append("\n" + "Total Payments: $" + new DecimalFormat("0.00").format((months - 1) * payment + finalPayment));
        analysisTextArea.append("\n" + "Interest Paid $" + new DecimalFormat("0.00").format((months - 1) * payment + finalPayment - balance));
        computeButton.setEnabled(false);
        newLoanButton.setEnabled(true);
        newLoanButton.requestFocus();
    }

    public boolean validateDecimalNumber(JTextField tf) {
        String s = tf.getText().trim();
        boolean hasDecimal = false;
        boolean valid = true;
        if (s.length() == 0) {
            valid = false;
        } else {
            for (int i = 0; i < s.length(); i++) {
                char c = s.charAt(i);
                if (c >= '0' && c <= '9') {
                    continue;
                } else if (c == '.' && !hasDecimal) {
                    hasDecimal = true;
                } else {
                    valid = false;
                }
            }
        }
        tf.setText(s);
        if (!valid) {
            tf.requestFocus();
        }
        return (valid);
    }

    public Main_Frame() {
        initComponents();
        this.computePayment = false;
        analysisTextArea.setEditable(false);
        monthsTextField.setBackground(Color.yellow);
        monthsButton.setVisible(false);
    }

    @SuppressWarnings("unchecked")
    // <editor-fold defaultstate="collapsed" desc="Generated Code">//GEN-BEGIN:initComponents
    private void initComponents() {

        jPanel2 = new javax.swing.JPanel();
        jPanel3 = new javax.swing.JPanel();
        balanceLabel = new javax.swing.JLabel();
        interestLabel = new javax.swing.JLabel();
        paymentLabel = new javax.swing.JLabel();
        monthsLabel = new javax.swing.JLabel();
        interestTextField = new javax.swing.JTextField();
        balanceTextField = new javax.swing.JTextField();
        paymentTextField = new javax.swing.JTextField();
        monthsTextField = new javax.swing.JTextField();
        computeButton = new javax.swing.JButton();
        paymentButton = new javax.swing.JButton();
        jScrollPane1 = new javax.swing.JScrollPane();
        analysisTextArea = new javax.swing.JTextArea();
        monthsButton = new javax.swing.JButton();
        analysisLabel = new javax.swing.JLabel();
        exitButton = new javax.swing.JButton();
        newLoanButton = new javax.swing.JButton();

        setDefaultCloseOperation(javax.swing.WindowConstants.EXIT_ON_CLOSE);
        setTitle("Loan Assisten");
        setBackground(new java.awt.Color(51, 51, 255));
        setResizable(false);

        jPanel2.setBackground(java.awt.SystemColor.window);
        jPanel2.setBorder(javax.swing.BorderFactory.createBevelBorder(javax.swing.border.BevelBorder.RAISED));
        jPanel2.setPreferredSize(new java.awt.Dimension(1046, 400));

        jPanel3.setBackground(new java.awt.Color(204, 204, 255));

        balanceLabel.setFont(new java.awt.Font("Arial", 0, 24)); // NOI18N
        balanceLabel.setText("Loan Balance");

        interestLabel.setFont(new java.awt.Font("Arial", 0, 24)); // NOI18N
        interestLabel.setText("Interest Rate");

        paymentLabel.setFont(new java.awt.Font("Arial", 0, 24)); // NOI18N
        paymentLabel.setText("Number of Payments");

        monthsLabel.setFont(new java.awt.Font("Arial", 0, 24)); // NOI18N
        monthsLabel.setText("Monthly Payent");

        interestTextField.setFont(new java.awt.Font("Arial", 0, 24)); // NOI18N
        interestTextField.setHorizontalAlignment(javax.swing.JTextField.RIGHT);
        interestTextField.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                interestTextFieldActionPerformed(evt);
            }
        });

        balanceTextField.setFont(new java.awt.Font("Arial", 0, 24)); // NOI18N
        balanceTextField.setHorizontalAlignment(javax.swing.JTextField.RIGHT);

        paymentTextField.setFont(new java.awt.Font("Arial", 0, 24)); // NOI18N
        paymentTextField.setHorizontalAlignment(javax.swing.JTextField.RIGHT);
        paymentTextField.setCursor(new java.awt.Cursor(java.awt.Cursor.TEXT_CURSOR));
        paymentTextField.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                paymentTextFieldActionPerformed(evt);
            }
        });

        monthsTextField.setFont(new java.awt.Font("Arial", 0, 24)); // NOI18N
        monthsTextField.setHorizontalAlignment(javax.swing.JTextField.RIGHT);
        monthsTextField.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                monthsTextFieldActionPerformed(evt);
            }
        });

        computeButton.setFont(new java.awt.Font("Arial", 1, 24)); // NOI18N
        computeButton.setText("Compute Number of Payments");
        computeButton.setBorder(javax.swing.BorderFactory.createBevelBorder(javax.swing.border.BevelBorder.RAISED));
        computeButton.setCursor(new java.awt.Cursor(java.awt.Cursor.DEFAULT_CURSOR));
        computeButton.setIconTextGap(1);
        computeButton.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                computeButtonActionPerformed(evt);
            }
        });

        paymentButton.setFont(new java.awt.Font("Tahoma", 0, 36)); // NOI18N
        paymentButton.setText("X");
        paymentButton.setAlignmentY(0.2F);
        paymentButton.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                paymentButtonActionPerformed(evt);
            }
        });

        analysisTextArea.setColumns(20);
        analysisTextArea.setFont(new java.awt.Font("Arial", 0, 18)); // NOI18N
        analysisTextArea.setRows(5);
        analysisTextArea.setMargin(new java.awt.Insets(20, 20, 20, 20));
        jScrollPane1.setViewportView(analysisTextArea);

        monthsButton.setFont(new java.awt.Font("Tahoma", 0, 36)); // NOI18N
        monthsButton.setText("X");
        monthsButton.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                monthsButtonActionPerformed(evt);
            }
        });

        analysisLabel.setFont(new java.awt.Font("Arial", 0, 24)); // NOI18N
        analysisLabel.setText("Loan Analysis :");

        exitButton.setFont(new java.awt.Font("Tahoma", 0, 24)); // NOI18N
        exitButton.setText("Exit");
        exitButton.setBorder(javax.swing.BorderFactory.createTitledBorder(""));
        exitButton.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                exitButtonActionPerformed(evt);
            }
        });

        newLoanButton.setFont(new java.awt.Font("Arial", 1, 24)); // NOI18N
        newLoanButton.setText("New Loan Analysis");
        newLoanButton.setBorder(javax.swing.BorderFactory.createBevelBorder(javax.swing.border.BevelBorder.RAISED));
        newLoanButton.setCursor(new java.awt.Cursor(java.awt.Cursor.DEFAULT_CURSOR));
        newLoanButton.setEnabled(false);
        newLoanButton.setFocusable(false);
        newLoanButton.setIconTextGap(1);
        newLoanButton.setName(""); // NOI18N
        newLoanButton.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                newLoanButtonActionPerformed(evt);
            }
        });

        javax.swing.GroupLayout jPanel3Layout = new javax.swing.GroupLayout(jPanel3);
        jPanel3.setLayout(jPanel3Layout);
        jPanel3Layout.setHorizontalGroup(
            jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(jPanel3Layout.createSequentialGroup()
                .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(jPanel3Layout.createSequentialGroup()
                        .addGap(34, 34, 34)
                        .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                            .addGroup(jPanel3Layout.createSequentialGroup()
                                .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                                    .addComponent(paymentLabel, javax.swing.GroupLayout.PREFERRED_SIZE, 262, javax.swing.GroupLayout.PREFERRED_SIZE)
                                    .addComponent(interestLabel, javax.swing.GroupLayout.PREFERRED_SIZE, 262, javax.swing.GroupLayout.PREFERRED_SIZE)
                                    .addComponent(balanceLabel, javax.swing.GroupLayout.PREFERRED_SIZE, 262, javax.swing.GroupLayout.PREFERRED_SIZE))
                                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                                .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                                    .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                                        .addComponent(balanceTextField, javax.swing.GroupLayout.PREFERRED_SIZE, 313, javax.swing.GroupLayout.PREFERRED_SIZE)
                                        .addComponent(interestTextField, javax.swing.GroupLayout.Alignment.TRAILING, javax.swing.GroupLayout.PREFERRED_SIZE, 313, javax.swing.GroupLayout.PREFERRED_SIZE))
                                    .addComponent(paymentTextField, javax.swing.GroupLayout.Alignment.TRAILING, javax.swing.GroupLayout.PREFERRED_SIZE, 313, javax.swing.GroupLayout.PREFERRED_SIZE))
                                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                                .addComponent(paymentButton))
                            .addGroup(jPanel3Layout.createSequentialGroup()
                                .addComponent(monthsLabel, javax.swing.GroupLayout.PREFERRED_SIZE, 262, javax.swing.GroupLayout.PREFERRED_SIZE)
                                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                                .addComponent(monthsTextField, javax.swing.GroupLayout.PREFERRED_SIZE, 313, javax.swing.GroupLayout.PREFERRED_SIZE)
                                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                                .addComponent(monthsButton))))
                    .addGroup(jPanel3Layout.createSequentialGroup()
                        .addGap(106, 106, 106)
                        .addComponent(computeButton, javax.swing.GroupLayout.PREFERRED_SIZE, 422, javax.swing.GroupLayout.PREFERRED_SIZE))
                    .addGroup(jPanel3Layout.createSequentialGroup()
                        .addGap(182, 182, 182)
                        .addComponent(newLoanButton, javax.swing.GroupLayout.PREFERRED_SIZE, 258, javax.swing.GroupLayout.PREFERRED_SIZE)))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, 27, Short.MAX_VALUE)
                .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, jPanel3Layout.createSequentialGroup()
                        .addComponent(exitButton, javax.swing.GroupLayout.PREFERRED_SIZE, 154, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addGap(112, 112, 112))
                    .addGroup(jPanel3Layout.createSequentialGroup()
                        .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                            .addComponent(jScrollPane1, javax.swing.GroupLayout.PREFERRED_SIZE, 332, javax.swing.GroupLayout.PREFERRED_SIZE)
                            .addGroup(jPanel3Layout.createSequentialGroup()
                                .addGap(8, 8, 8)
                                .addComponent(analysisLabel, javax.swing.GroupLayout.PREFERRED_SIZE, 220, javax.swing.GroupLayout.PREFERRED_SIZE)))
                        .addContainerGap(44, Short.MAX_VALUE))))
        );
        jPanel3Layout.setVerticalGroup(
            jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.TRAILING)
            .addGroup(jPanel3Layout.createSequentialGroup()
                .addContainerGap(29, Short.MAX_VALUE)
                .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, jPanel3Layout.createSequentialGroup()
                        .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                            .addComponent(balanceLabel, javax.swing.GroupLayout.PREFERRED_SIZE, 67, javax.swing.GroupLayout.PREFERRED_SIZE)
                            .addComponent(balanceTextField, javax.swing.GroupLayout.PREFERRED_SIZE, 58, javax.swing.GroupLayout.PREFERRED_SIZE))
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED))
                    .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, jPanel3Layout.createSequentialGroup()
                        .addComponent(analysisLabel, javax.swing.GroupLayout.PREFERRED_SIZE, 79, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addGap(15, 15, 15)))
                .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(jPanel3Layout.createSequentialGroup()
                        .addComponent(jScrollPane1, javax.swing.GroupLayout.PREFERRED_SIZE, 300, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                            .addGroup(jPanel3Layout.createSequentialGroup()
                                .addGap(25, 25, 25)
                                .addComponent(newLoanButton, javax.swing.GroupLayout.PREFERRED_SIZE, 51, javax.swing.GroupLayout.PREFERRED_SIZE)
                                .addContainerGap())
                            .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, jPanel3Layout.createSequentialGroup()
                                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                                .addComponent(exitButton, javax.swing.GroupLayout.PREFERRED_SIZE, 45, javax.swing.GroupLayout.PREFERRED_SIZE)
                                .addGap(30, 30, 30))))
                    .addGroup(jPanel3Layout.createSequentialGroup()
                        .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                            .addGroup(jPanel3Layout.createSequentialGroup()
                                .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                                    .addComponent(interestLabel, javax.swing.GroupLayout.PREFERRED_SIZE, 67, javax.swing.GroupLayout.PREFERRED_SIZE)
                                    .addComponent(interestTextField, javax.swing.GroupLayout.PREFERRED_SIZE, 58, javax.swing.GroupLayout.PREFERRED_SIZE))
                                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                                .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                                    .addComponent(paymentLabel, javax.swing.GroupLayout.PREFERRED_SIZE, 69, javax.swing.GroupLayout.PREFERRED_SIZE)
                                    .addComponent(paymentTextField, javax.swing.GroupLayout.PREFERRED_SIZE, 58, javax.swing.GroupLayout.PREFERRED_SIZE))
                                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, 8, Short.MAX_VALUE)
                                .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                                    .addComponent(monthsLabel, javax.swing.GroupLayout.PREFERRED_SIZE, 67, javax.swing.GroupLayout.PREFERRED_SIZE)
                                    .addComponent(monthsTextField, javax.swing.GroupLayout.PREFERRED_SIZE, 58, javax.swing.GroupLayout.PREFERRED_SIZE))
                                .addGap(29, 29, 29)
                                .addComponent(computeButton, javax.swing.GroupLayout.PREFERRED_SIZE, 51, javax.swing.GroupLayout.PREFERRED_SIZE))
                            .addGroup(jPanel3Layout.createSequentialGroup()
                                .addGap(79, 79, 79)
                                .addComponent(paymentButton, javax.swing.GroupLayout.PREFERRED_SIZE, 58, javax.swing.GroupLayout.PREFERRED_SIZE)
                                .addGap(18, 18, 18)
                                .addComponent(monthsButton, javax.swing.GroupLayout.PREFERRED_SIZE, 58, javax.swing.GroupLayout.PREFERRED_SIZE)
                                .addGap(0, 0, Short.MAX_VALUE)))
                        .addGap(102, 102, 102))))
        );

        javax.swing.GroupLayout jPanel2Layout = new javax.swing.GroupLayout(jPanel2);
        jPanel2.setLayout(jPanel2Layout);
        jPanel2Layout.setHorizontalGroup(
            jPanel2Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, jPanel2Layout.createSequentialGroup()
                .addContainerGap()
                .addComponent(jPanel3, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                .addContainerGap())
        );
        jPanel2Layout.setVerticalGroup(
            jPanel2Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(jPanel2Layout.createSequentialGroup()
                .addContainerGap()
                .addComponent(jPanel3, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addContainerGap(14, Short.MAX_VALUE))
        );

        javax.swing.GroupLayout layout = new javax.swing.GroupLayout(getContentPane());
        getContentPane().setLayout(layout);
        layout.setHorizontalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addComponent(jPanel2, javax.swing.GroupLayout.DEFAULT_SIZE, 1105, Short.MAX_VALUE)
        );
        layout.setVerticalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addComponent(jPanel2, javax.swing.GroupLayout.DEFAULT_SIZE, 554, Short.MAX_VALUE)
        );

        setSize(new java.awt.Dimension(1123, 601));
        setLocationRelativeTo(null);
    }// </editor-fold>//GEN-END:initComponents

    private void interestTextFieldActionPerformed(java.awt.event.ActionEvent evt) {//GEN-FIRST:event_interestTextFieldActionPerformed
        // TODO add your handling code here:
    }//GEN-LAST:event_interestTextFieldActionPerformed

    private void paymentTextFieldActionPerformed(java.awt.event.ActionEvent evt) {//GEN-FIRST:event_paymentTextFieldActionPerformed
        // TODO add your handling code here:
    }//GEN-LAST:event_paymentTextFieldActionPerformed

    private void monthsTextFieldActionPerformed(java.awt.event.ActionEvent evt) {//GEN-FIRST:event_monthsTextFieldActionPerformed
        // TODO add your handling code here:
    }//GEN-LAST:event_monthsTextFieldActionPerformed

    private void exitButtonActionPerformed(java.awt.event.ActionEvent evt) {//GEN-FIRST:event_exitButtonActionPerformed
        System.exit(0);
    }//GEN-LAST:event_exitButtonActionPerformed

    private void computeButtonActionPerformed(java.awt.event.ActionEvent evt) {//GEN-FIRST:event_computeButtonActionPerformed
        computeButtonActionPerformed();
    }//GEN-LAST:event_computeButtonActionPerformed

    private void newLoanButtonActionPerformed(java.awt.event.ActionEvent evt) {//GEN-FIRST:event_newLoanButtonActionPerformed
        newLoanCkicked();
    }//GEN-LAST:event_newLoanButtonActionPerformed

    private void paymentButtonActionPerformed(java.awt.event.ActionEvent evt) {//GEN-FIRST:event_paymentButtonActionPerformed
        computePayment = true;
        paymentButton.setVisible(false);
        monthsButton.setVisible(true);
        monthsTextField.setEditable(true);
        monthsTextField.setBackground(Color.WHITE);
        paymentTextField.setText("");
        paymentTextField.setEditable(false);
        paymentTextField.setBackground(Color.yellow);
        computeButton.setText("Compute Monthly Payment");
    }//GEN-LAST:event_paymentButtonActionPerformed

    private void monthsButtonActionPerformed(java.awt.event.ActionEvent evt) {//GEN-FIRST:event_monthsButtonActionPerformed
       
        computePayment = false;
        paymentButton.setVisible(true);
        monthsButton.setVisible(false);
        monthsTextField.setText("");
        monthsTextField.setEditable(false);
        monthsTextField.setBackground(Color.yellow);
        paymentTextField.setEditable(true);
        paymentTextField.setBackground(Color.WHITE);
        computeButton.setText("Compute Number of Payments");

    }//GEN-LAST:event_monthsButtonActionPerformed

    /**
     * @param args the command line arguments
     */
    public static void main(String args[]) {
       
        java.awt.EventQueue.invokeLater(new Runnable() {
            @Override
            public void run() {
                new Main_Frame().setVisible(true);
            }
        });
    }

    // Variables declaration - do not modify//GEN-BEGIN:variables
    private javax.swing.JLabel analysisLabel;
    private javax.swing.JTextArea analysisTextArea;
    private javax.swing.JLabel balanceLabel;
    private javax.swing.JTextField balanceTextField;
    private javax.swing.JButton computeButton;
    private javax.swing.JButton exitButton;
    private javax.swing.JLabel interestLabel;
    private javax.swing.JTextField interestTextField;
    private javax.swing.JPanel jPanel2;
    private javax.swing.JPanel jPanel3;
    private javax.swing.JScrollPane jScrollPane1;
    private javax.swing.JButton monthsButton;
    private javax.swing.JLabel monthsLabel;
    private javax.swing.JTextField monthsTextField;
    private javax.swing.JButton newLoanButton;
    private javax.swing.JButton paymentButton;
    private javax.swing.JLabel paymentLabel;
    private javax.swing.JTextField paymentTextField;
    // End of variables declaration//GEN-END:variables
}
