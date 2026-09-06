package calculadora;

import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;

public class CalculadoraGUI extends JFrame {

    private JTextField txtNumero1;
    private JTextField txtNumero2;
    private JTextField txtResultado;

    public CalculadoraGUI() {
        setTitle("Calculadora Básica");
        setSize(430, 320);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLocationRelativeTo(null);
        setResizable(false);

        iniciarComponentes();
    }

    private void iniciarComponentes() {
        JPanel panel = new JPanel();
        panel.setLayout(null);
        add(panel);

        JLabel lblTitulo = new JLabel("Calculadora Básica");
        lblTitulo.setFont(new Font("Arial", Font.BOLD, 22));
        lblTitulo.setBounds(115, 15, 220, 30);
        panel.add(lblTitulo);

        JLabel lblNumero1 = new JLabel("Número 1:");
        lblNumero1.setBounds(35, 65, 90, 25);
        panel.add(lblNumero1);

        txtNumero1 = new JTextField();
        txtNumero1.setBounds(125, 65, 230, 25);
        panel.add(txtNumero1);

        JLabel lblNumero2 = new JLabel("Número 2:");
        lblNumero2.setBounds(35, 105, 90, 25);
        panel.add(lblNumero2);

        txtNumero2 = new JTextField();
        txtNumero2.setBounds(125, 105, 230, 25);
        panel.add(txtNumero2);

        JLabel lblResultado = new JLabel("Resultado:");
        lblResultado.setBounds(35, 145, 90, 25);
        panel.add(lblResultado);

        txtResultado = new JTextField();
        txtResultado.setBounds(125, 145, 230, 25);
        txtResultado.setEditable(false);
        panel.add(txtResultado);

        JButton btnSumar = new JButton("Sumar");
        btnSumar.setBounds(25, 200, 85, 30);
        btnSumar.addActionListener(this::sumar);
        panel.add(btnSumar);

        JButton btnRestar = new JButton("Restar");
        btnRestar.setBounds(115, 200, 85, 30);
        btnRestar.addActionListener(this::restar);
        panel.add(btnRestar);

        JButton btnMultiplicar = new JButton("Multiplicar");
        btnMultiplicar.setBounds(205, 200, 100, 30);
        btnMultiplicar.addActionListener(this::multiplicar);
        panel.add(btnMultiplicar);

        JButton btnDividir = new JButton("Dividir");
        btnDividir.setBounds(310, 200, 85, 30);
        btnDividir.addActionListener(this::dividir);
        panel.add(btnDividir);

        JButton btnRaiz = new JButton("Raíz cuadrada");
        btnRaiz.setBounds(125, 240, 140, 30);
        btnRaiz.addActionListener(this::raizCuadrada);
        panel.add(btnRaiz);
    }

    private double leerNumero(JTextField campo) throws NumberFormatException {
        String texto = campo.getText().trim();

        if (texto.isEmpty()) {
            throw new NumberFormatException();
        }

        return Double.parseDouble(texto);
    }

    private void sumar(ActionEvent e) {
        try {
            double n1 = leerNumero(txtNumero1);
            double n2 = leerNumero(txtNumero2);
            txtResultado.setText(String.valueOf(n1 + n2));
        } catch (NumberFormatException ex) {
            mostrarError();
        }
    }

    private void restar(ActionEvent e) {
        try {
            double n1 = leerNumero(txtNumero1);
            double n2 = leerNumero(txtNumero2);
            txtResultado.setText(String.valueOf(n1 - n2));
        } catch (NumberFormatException ex) {
            mostrarError();
        }
    }

    private void multiplicar(ActionEvent e) {
        try {
            double n1 = leerNumero(txtNumero1);
            double n2 = leerNumero(txtNumero2);
            txtResultado.setText(String.valueOf(n1 * n2));
        } catch (NumberFormatException ex) {
            mostrarError();
        }
    }

    private void dividir(ActionEvent e) {
        try {
            double n1 = leerNumero(txtNumero1);
            double n2 = leerNumero(txtNumero2);

            if (n2 == 0) {
                JOptionPane.showMessageDialog(this,
                        "No se puede dividir entre cero.",
                        "Error",
                        JOptionPane.ERROR_MESSAGE);
                return;
            }

            txtResultado.setText(String.valueOf(n1 / n2));
        } catch (NumberFormatException ex) {
            mostrarError();
        }
    }

    private void raizCuadrada(ActionEvent e) {
        try {
            double n1 = leerNumero(txtNumero1);

            if (n1 < 0) {
                JOptionPane.showMessageDialog(this,
                        "No se puede calcular la raíz cuadrada de un número negativo.",
                        "Error",
                        JOptionPane.ERROR_MESSAGE);
                return;
            }

            txtResultado.setText(String.valueOf(Math.sqrt(n1)));
        } catch (NumberFormatException ex) {
            JOptionPane.showMessageDialog(this,
                    "Ingrese un número válido en el primer campo.",
                    "Dato inválido",
                    JOptionPane.WARNING_MESSAGE);
        }
    }

    private void mostrarError() {
        JOptionPane.showMessageDialog(this,
                "Ingrese valores numéricos válidos.",
                "Dato inválido",
                JOptionPane.WARNING_MESSAGE);
    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(() -> {
            CalculadoraGUI ventana = new CalculadoraGUI();
            ventana.setVisible(true);
        });
    }
}
