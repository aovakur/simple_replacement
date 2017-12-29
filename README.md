Задача: разработать программу, которая будет заменять символы шифруемого текста на символы того же алфавита со сдвигом вправо на два символа. 

![picture](https://github.com/aovakur/simple_replacement/blob/master/img.jpg)

Код программы

using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace WindowsFormsApplication1
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
            
        }

        public string line;
        public int l;
        public int j,i= 0;
        public char translate_char;
        public string translate;
        public char[] translate_word;
        public char[] ru_alphabet = { 'а', 'б', 'в', 'г','д','е', 'ё', 'ж', 'з', 'и', 'й', 'к', 'л', 'м', 'н', 'о', 'п', 'р', 'с', 'т', 'у', 'ф', 'х', 'ц', 'ч', 'ш', 'щ', 'ъ', 'ы','ь', 'э', 'ю', 'я'};
        public char[] eng_alphabet = { 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z'};
        private void button1_Click(object sender, EventArgs e)
        {
          
            if (checkBox1.Checked == true)
            {
                
                line = textBox1.Text.ToLower();
                for (int i = 0; i < line.Length; i++)
                {
                    translate_char = line[i];

                    for (int j = 0; j < 33; j++)
                        if (translate_char== ru_alphabet[j])
                           {

                            if (translate_char != ru_alphabet[31] && translate_char != ru_alphabet[32])
                            {
                                translate = translate + ru_alphabet[j + 2];
                                textBox2.Text = Convert.ToString(translate);
                            }

                            if (translate_char == ru_alphabet[32])
                            {
                                translate = translate + ru_alphabet[j + 2];
                                textBox2.Text = Convert.ToString(translate);
                            }

                            if (translate_char == ru_alphabet[31])
                            {
                                translate = translate + ru_alphabet[j + 2];
                                textBox2.Text = Convert.ToString(translate);
                            }
                           }
                }
            }

            if (checkBox2.Checked == true)
            {
                checkBox1.Visible = false;
                line = textBox1.Text.ToLower();
                for (int i = 0; i < line.Length; i++)
                {
                    translate_char = line[i];

                    for (int j = 0; j < 26; j++)

                        if (translate_char == eng_alphabet[j])
                        {
                            if (translate_char != eng_alphabet[24] && translate_char != eng_alphabet[25] )
                            {
                                translate = translate + eng_alphabet[j + 2];
                                textBox2.Text = Convert.ToString(translate);
                            }

                            if (translate_char == eng_alphabet[24])
                            {
                                translate = translate + eng_alphabet[1];
                                textBox2.Text = Convert.ToString(translate);
                            }

                            if (translate_char == eng_alphabet[25])
                            {
                                translate = translate + eng_alphabet[2];
                                textBox2.Text = Convert.ToString(translate);
                            }
                        }
                }


            }

        }


        private void button2_Click(object sender, EventArgs e)
        {
            textBox2.Text = "";
            translate = "";
            }

        private void checkBox1_CheckedChanged(object sender, EventArgs e)
        {

        }
    }
}
