#include <iostream>
#include <fstream>
#include <string>
#include <iomanip>
#include <bitset>

//adding namespace for main integer

using namespace std;

void menu(int msg);

int main()

{

    menu(0);        

    return 0;

}

void menu(int msg)

{ system("CLS");

    if(msg==0)

    {

        //adding the text that will apear on the output screeen

        cout<<"Welcome to Text Editor"<<endl<<endl;

    }

       

    //Adding the main commands to choose from, in the output sector

    cout<<"Main Menu"<<endl;

    cout<<"-------------"<<endl;

    cout<<"1. Create File"<<endl;

    cout<<"2. Edit File"<<endl;

    cout<<"3. Read from File"<<endl;

    cout<<"4. Delete File"<<endl;

    cout<<"5. Hexadecimal form of file" <<endl;

    cout <<"6. Binary form of file" <<endl;

    cout <<"7. ASCII character form of file" <<endl;

    cout<<"8. Exit"<<endl<<endl;

    cout<<"Enter Choice: ";

   

    int choice = 0;

    string filename;    

    string text;    

           

    cin>>choice;

    if(choice==1)

    {  

        //first choice is to create a file by making a file and then naming it

        cout<<endl<<"Enter name of file: ";    

        cin.ignore();

        getline(cin, filename);

        ofstream myfile( (filename+".txt").c_str() );

        // c_str() is used to convert contents of the string to designated functions

        myfile.close();    

        menu(1);        

        cin>>choice;

    }

    if(choice==2)

    {

        //the following choice edits the created file

        text="";

        cout<<endl<<"Enter name of file: ";

        cin>>filename;      

        cout<<endl<<"Enter text to write to file: (Enter END to complete)"<<endl;

        ofstream myfile;

        myfile.open((filename+".txt").c_str(),ios::app);            

        string line;

        cin.ignore();  

        // cin.ignore()  ignores the temporary contents

        while (getline(cin, line))

        {

            if(line.size()>=3)

            {          

                if (line.substr(line.size() - 3) == "END")

                // writing END after a string that is to be added in the file will end the function

                {

                    text += line.substr(0, line.size()-3);

                    break;  

                }  

                else{

                    text += line+"\n";

                    // \n put the next function from the next line

                }

            }

            else{

                text += line+"\n";

            }                  

        }

        myfile<<text;

        myfile.close();

        menu(2);        

        cin>>choice;

    }

    if(choice==3)

    {

        // choice 3 will help us review all the contentpresent in the file, thus reading it

        text="";

        cout<<endl<<"Enter name of file: ";

        cin>>filename;      

        fstream myfile;

        myfile.open((filename+".txt").c_str());        

        while(getline(myfile, text)){

         cout << text << "\n";

        }

        myfile.close();

        char now;

        cout<<endl<<"End of File. Press any key for main menu: ";

        cin>>now;      

        menu(2);        

        cin>>choice;

    }

   

    if(choice==4)

    {

        // choice 4 will delete the content of the file and the file as well

        cout<<endl<<"Enter name of file: ";

        cin>>filename;      

        if (remove((filename+".txt").c_str())==0)

        {

            menu(5);                

        }      

        else

        {

            menu(55);  

        }          

    }

   

    if(choice==8)

    {

        // choice 8 will help us exit from the program entirely

        exit(EXIT_SUCCESS);

    }
   
    
    {

using namespace std;
if (choice==5)
{
     cout<<endl<<"Enter name of file: ";

        cin>>filename;      

        fstream myfile;

        myfile.open((filename+".txt").c_str());  
  void convertFileToHex(const std::string& filePath) ;
  {
    std::ifstream file;( std::ios::binary);
    if (!file) {
        std::cerr << "Unable to open file: "  << std::endl;
        return;
    }

    std::cout << "Hexadecimal representation of the file: " << std::endl;

    char byte;
    while (file.read(&byte, 1)) {
        std::cout << std::hex << std::setw(2) << std::setfill('0') << (int)byte;
    }

    std::cout << std::endl;
}



}
}
if (choice==6)
{
     cout<<endl<<"Enter name of file: ";

        cin>>filename;      

        fstream myfile;

        myfile.open((filename+".txt").c_str());
        void convertFileToBinary(const std::string& filePath);
        {
    std::ifstream file; std::ios::binary;
    ;
    if (!file) {
        std::cerr << "Unable to open file: " << std::endl;
        return;
    }

    std::cout << "Binary representation of the file: " << std::endl;

    char byte;
    while (file.read(&byte, 1)) {
        for (int i = 7; i >= 0; --i) {
            std::cout << ((byte >> i) & 1);
        }
    }

    std::cout << std::endl;
}
}
if (choice==7)
{
     cout<<endl<<"Enter name of file: ";

        cin>>filename;      

        fstream myfile;

        myfile.open((filename+".txt").c_str());  
        void convertFileToAscii(const std::string& filePath); {
    std::ifstream file;
    if (!file) {
        std::cerr << "Unable to open file: " << std::endl;
        return;
    }

    std::cout << "ASCII representation of the file:";
}
}
}
