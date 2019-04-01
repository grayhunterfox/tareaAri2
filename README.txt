Para leer los admins se usa algo del tipo:



using System;
using System.Xml;
namespace xmltest
{
    class Program
    {
        static void Main(string[] args)        // NOTAR QUE ESTÁ EN MAIN, HAY QUE HACERLO FUNCION.
        {
            XmlDocument xDoc = new XmlDocument();
            //La ruta del documento XML permite rutas relativas respecto del ejecutable

            xDoc.Load("C:/Users/Kitsune/Documents/ARI/tarea 2/admin.xml");

            XmlNodeList admins = xDoc.GetElementsByTagName("admins");
            XmlNodeList lista = ((XmlElement)admins[0]).GetElementsByTagName("admin");

            foreach (XmlElement nodo in lista)
            {
                int i = 0;
                XmlNodeList nombre = nodo.GetElementsByTagName("nombre");
                XmlNodeList edad = nodo.GetElementsByTagName("edad");

                Console.WriteLine("Admin es: {0}, edad {1} años.\n",
                                             nombre[i].InnerText,
                                             edad[i].InnerText);
            }
            Console.Read();
        }
    }
}
