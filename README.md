# PE-2
Proyecto
 public static int Mayore(int[]vocho,int nukes)
        {
            int mayor;
            if(nukes==0)
            {
                return vocho[nukes];
            }
            else
            {
                mayor = Mayore(vocho, nukes - 1);
                if(vocho[nukes]>mayor)
                {
                    return vocho[nukes];
                }
                else
                {
                    return Mayore(vocho, nukes - 1);
                }
            }
        }
        public static int Menore(int [] vip, int nuc, int minus)
        {
            
            if (nuc == 0)
            {
                if (minus > vip[nuc])
                {
                    return vip[0];
                }
                else
                {
                    return minus;
                }
            }
            else
            {
                if (minus > vip[nuc])
                {
                    return Menore(vip, nuc - 1, vip[nuc]);
                }
                else
                {
                    return Menore(vip, nuc - 1, minus);
                }
            }
        }
        static public string Invertido(int four)
        {
            if (four < 10)
                return four.ToString();
            else
                return (four % 10).ToString() + Invertido(four / 10);
        }
        static void Main(string[] args)
        {
            Console.ForegroundColor = ConsoleColor.Black;
            Console.BackgroundColor = ConsoleColor.White;
            Console.Clear();
            Random pat = new Random();
            int op = 0;
            while (op != 4)
            {
                Console.WriteLine("1.-Minimo.");
                Console.WriteLine("2.-Maximo.");
                Console.WriteLine("3.-Invertido.");
                Console.WriteLine("-Presione el boton 4 para salir.-");
                op = int.Parse(Console.ReadLine());
                Console.Clear();
                switch (op)
                {
                    case 1:
                        int nukes = 0;
                        Console.WriteLine("Ingrese cantidad de numeros: ");
                        nukes = int.Parse(Console.ReadLine());
                        Console.WriteLine();
                        int[] Vocho = new int[nukes];
                        for (int n = 0; n < Vocho.Length; n++)
                        {
                            Vocho[n] = pat.Next(1, 30);
                            Console.WriteLine(Vocho[n]);
                        }
                Console.WriteLine("El numero maximo es:" + Mayore(Vocho, nukes - 1));
                Console.WriteLine();
                        break;
                    case 2:
                        int nucas = 0;
                        Console.WriteLine("Ingrese cantidad de numeros: ");
                        nucas = int.Parse(Console.ReadLine());
                        Console.WriteLine();
                        int[] Viper = new int[nucas];
                        for (int u = 0; u < Viper.Length; u++)
                        {
                            Viper[u] = pat.Next(1, 30);
                            Console.WriteLine(Viper[u]);
                        }
                        Console.WriteLine("El numero minimo es:" + Menore(Viper, nucas - 1, Viper[0]));
                        Console.WriteLine();
                        break;
                    case 3:
                        int locas = 0;
                        Console.WriteLine("Ingrese cantidad: ");
                        locas =int.Parse(Console.ReadLine());
                        Console.WriteLine("Cantidad invertida: "+Invertido(locas));
                        Console.WriteLine();
                        break;
                 }
            }
            Console.ReadKey();
        }
