# caluculator_1
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Animation;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;

namespace calculator_assignment
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            
        }

        private void zero_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + "0";
        }

        private void point_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + ".";

        }

        private void clear_Click(object sender, RoutedEventArgs e)
        {
            screen.Text =  "";

        }

        private void one_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + "1";

        }

        private void two_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + "2";

        }

        private void three_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + "3";

        }

        private void four_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + "4";

        }

        private void five_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + "5";

        }

        private void six_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + "6";

        }

        private void seven_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + "7";

        }

        private void eight_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + "8";

        }

        private void nine_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + "9";

        }

        private void lpar_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + "(";

        }

        private void rpar_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + ")";

        }

        private void plus_Click(object sender, RoutedEventArgs e)
        {

            screen.Text = screen.Text + "+";

        }

        private void minus_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + "-";

        }

        private void multi_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + "*";

        }

        private void division_Click(object sender, RoutedEventArgs e)
        {
            screen.Text = screen.Text + "/";

        }

        private void result_Click(object sender, RoutedEventArgs e)
        {
            Type scriptType = Type.GetTypeFromCLSID(Guid.Parse("0E59F1D5-1FBE-11D0-8FF2-00A0D10038BC"));
            dynamic obj = Activator.CreateInstance(scriptType,false);
            obj.Language = "javascript";
            String str = null;

            try
            {
                var res = obj.Eval(screen.Text);
                str = Convert.ToString(res);
                screen.Text = screen.Text + "=" + str;

            }
            catch(SystemException)
            {
                screen.Text = "syntax error";
                
            }


        }

        private void button_Copy18_Click(object sender, RoutedEventArgs e)
        {
            if (screen.Text != "")
                screen.Text = screen.Text.Remove(screen.Text.Length - 1);
        }
        private int caluculate_Factorial(int num)
        {
            int answer = 1;
            for (int x = 1; x <= num; x = x + 1)
                answer = answer * x;
            return answer;

        }
        private void button_Click(object sender, RoutedEventArgs e)
        {
            
            try
            {

                int fact, answer;
                fact = int.Parse(screen.Text);
                answer = caluculate_Factorial(fact);
                screen.Text = answer.ToString();
                screen.IsReadOnlyCaretVisible = true;
            }
            catch (SystemException)
            {
                screen.Text = "syntax error";

            }
        }

        private void button1_Click(object sender, RoutedEventArgs e)
        {
            
            try
            {
                screen.Text = Convert.ToString(Math.Sqrt(Convert.ToDouble(screen.Text)));


            }
            catch (SystemException)
            {
                screen.Text = "syntax error";

            }
        }
    }
}
