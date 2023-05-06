# h-t-08-05

#include <iostream>
using namespace std;

template <typename T>
class MATRIX
{
    T a;
    T b;
    T** M1 = new T * [3]; 
    T** M2 = new T * [3]; 
    T** MI = new T * [3]; 
    
    //---------------------------------------
    friend MATRIX operator +(MATRIX& a1, MATRIX& b1)
    {
        return MATRIX { a1.a + b1.b};
    }
    friend MATRIX operator -(MATRIX& a1, MATRIX& b1)
    {
        return MATRIX { a1.a - b1.b};
    }
    friend MATRIX operator *(MATRIX& a1, MATRIX& b1)
    {
        return MATRIX { a1.a * b1.b};
    }
    friend MATRIX operator /(MATRIX& a1, MATRIX& b1)
    {
        return MATRIX { a1.a / b1.b};
    }
    //---------------------------------------
    
    void EnterPrint()
    {
        //first matrix
        cout << "   Enter first matrix's data: " << endl;
        for (int i = 0; i < 3; i++)
        {
            M1[i] = new T[i];
        }
        for (int i = 0; i < 3; i++)
        {
            for (int j = 0; j < 3; j++)
            {
                cin >> M1[i][j];
                cout << M1[i][j];
            }
            cout << endl;
        }
        //cout << endl;
        //second matrix
        cout << "   Enter second matrix's data: " << endl;
        for (int i = 0; i < 3; i++)
        {
            M2[i] = new T[i];
        }
        for (int i = 0; i < 3; i++)
        {
            for (int j = 0; j < 3; j++)
            {
                cin >> M2[i][j];
                cout << M2[i][j];
            }
            cout << endl;
        }
    }
        //operations----
        void AddM1()
        {
            cout << "Addition: " << endl;
            for (int i = 0; i < 3; i++)
            {
                MI[i] = new T[i];
            }
            for (int i = 0; i < 3; i++)
            {
                for (int j = 0; j < 3; j++)
                {
                    MI[i][j] = M1[i][j] + M2[i][j];
                    cout << MI[i][j];
                }
                cout << endl;
            }
        }
        void SubM1()
        {
            cout << "Substraction: " << endl;
            for (int i = 0; i < 3; i++)
            {
                MI[i] = new T[i];
            }
            for (int i = 0; i < 3; i++)
            {
                for (int j = 0; j < 3; j++)
                {
                    MI[i][j] = M1[i][j] - M2[i][j];
                    cout << MI[i][j];
                }
                cout << endl;
            }
        }
        void MulM1()
        {
            cout << "Multiplication: " << endl;
            for (int i = 0; i < 3; i++)
            {
                MI[i] = new T[i];
            }
            for (int i = 0; i < 3; i++)
            {
                for (int j = 0; j < 3; j++)
                {
                    MI[i][j] = M1[i][j] * M2[i][j];
                    cout << MI[i][j];
                }
                cout << endl;
            }
        }
        void DivM1()
        {
            cout << "Division: " << endl;
            for (int i = 0; i < 3; i++)
            {
                MI[i] = new T[i];
            }
            for (int i = 0; i < 3; i++)
            {
                for (int j = 0; j < 3; j++)
                {
                    MI[i][j] = M1[i][j] / M2[i][j];
                    cout << MI[i][j];
                }
                cout << endl;
            }
        }
        //delete
        void DeleteM()
        {
            for (int i = 0; i < 5; i++)
            {
                delete[] M1[i];
            }
            delete[] M1;
            for (int i = 0; i < 5; i++)
            {
                delete[] M2[i];
            }
            delete[] M2;
            for (int i = 0; i < 5; i++)
            {
                delete[] MI[i];
            }
            delete[] MI;
        }
};
//=================================================================================

template <typename T>
class ARR
{
    T a;
    T b;
    T** A1 = new T * [3]; // arr
    T** A2 = new T * [3]; // random
    T** AI = new T * [3]; //mass
    
    //---------------------------------------
    friend ARR operator +(ARR& a1, ARR& b1)
    {
        return ARR { a1.a + b1.b};
    }
    friend ARR operator -(ARR& a1, ARR& b1)
    {
        return ARR { a1.a - b1.b};
    }
    friend ARR operator *(ARR& a1, ARR& b1)
    {
        return ARR { a1.a * b1.b};
    }
    friend ARR operator /(ARR& a1, ARR& b1)
    {
        return ARR { a1.a / b1.b};
    }
    //---------------------------------------
    void RANDOM()
    {
        //srand(time(NULL));
        int maxA1 = 0;
        int minA1 = 0;
        int maxA2 = 0;
        int minA2 = 0;
        cout << "   First Array: " << endl;
        for (int i = 0; i < 3; i++) 
        {
            A1[i] = new T[i];
        }
        for (int i = 0; i < 5; i++) 
        {
            for (int j = 0; j < 5; j++)
            {
                A1[i][j] = rand()%10;
                cout << A1[i][j];
                if (maxA1 > A1[i][j])
                {
                    maxA1 = A1[i][j];
                }
                if (minA1 < A1[i][j])
                {
                    minA1 = A1[i][j];
                }
            }
            cout << endl;
        }
        cout << "Max - " << maxA1 << endl;
        cout << "Min - " << minA1 << endl;
        cout << endl;
        //
        cout << "   Second Array: \n";
        for (int i = 0; i < 3; i++)
        {
            A2[i] = new T[i];
        }
        for (int i = 0; i < 3; i++)
        {
            for (int j = 0; j < 3; j++)
            {
                A2[i][j] = rand()%15;
                cout << A2[i][j];
                if (maxA2 > A2[i][j])
                {
                    maxA2 = A2[i][j];
                }
                if (minA2 < A2[i][j])
                {
                    minA2 = A2[i][j];
                }
            }
            cout << endl;
        }
        cout << "Max- " << maxA2 << endl;
        cout << "Min - " << minA2 << endl;
        cout << endl;
    }
        //operations----
        void AddA1()
        {
            cout << "Addition: " << endl;
            for (int i = 0; i < 3; i++)
            {
                AI[i] = new T[i];
            }
            for (int i = 0; i < 3; i++)
            {
                for (int j = 0; j < 3; j++)
                {
                    AI[i][j] = A1[i][j] + A2[i][j];
                    cout << AI[i][j];
                }
                cout << endl;
            }
        }
        void SubA1()
        {
            cout << "Substraction: " << endl;
            for (int i = 0; i < 3; i++)
            {
                AI[i] = new T[i];
            }
            for (int i = 0; i < 3; i++)
            {
                for (int j = 0; j < 3; j++)
                {
                    AI[i][j] = A1[i][j] - A2[i][j];
                    cout << AI[i][j];
                }
                cout << endl;
            }
        }
        void MulA1()
        {
            cout << "Multiplication: " << endl;
            for (int i = 0; i < 3; i++)
            {
                AI[i] = new T[i];
            }
            for (int i = 0; i < 3; i++)
            {
                for (int j = 0; j < 3; j++)
                {
                    AI[i][j] = A1[i][j] * A2[i][j];
                    cout << AI[i][j];
                }
                cout << endl;
            }
        }
        void DivA1()
        {
            cout << "Division: " << endl;
            for (int i = 0; i < 3; i++)
            {
                AI[i] = new T[i];
            }
            for (int i = 0; i < 3; i++)
            {
                for (int j = 0; j < 3; j++)
                {
                    AI[i][j] = A1[i][j] / A2[i][j];
                    cout << AI[i][j];
                }
                cout << endl;
            }
        }
        //delete
        void DeleteA()
        {
            for (int i = 0; i < 5; i++)
            {
                delete[] A1[i];
            }
            delete[] A1;
            for (int i = 0; i < 5; i++)
            {
                delete[] A2[i];
            }
            delete[] A2;
            for (int i = 0; i < 5; i++)
            {
                delete[] AI[i];
            }
            delete[] AI;
        }
};
int main()
{
    MATRIX<int>a;
    ARR<int>b;
    int c1;
    int c;
    int c2;
    cout << "   Select: self-set or random? " << endl;
    cout << "1. Random" << endl;
    cout << "2. Create" << endl;
    cout << "3. Other" << endl ;
    do {
        cin >> c1;
        switch (c1)
        {
        case 1: (c1 == 1);
        {
            a.RANDOM();
            cout << endl;
            cout << "1. Addition" << endl;
            cout << "2. Substraction" << endl;
            cout << "3. Multiplication" << endl;
            cout << "4. Division" << endl;
            cout << "5. exit" << endl;
            do {
                cin >> c;
                switch (c) 
                {
                case 1: (c == 1);
                {
                    a.AddA1();
                    break;
                }
                case 2: (c == 2);
                {
                    a.SubA1;
                    break;
                }
                case 3: (c == 3);
                {
                    a.MulA1();
                    break;
                }
                case 4: (c == 4); 
                {
                    a.DivA1();
                    break;
                }
                case 5: (c == 5);
                {
                    a.DeleteA
                    break;
                }
                default:
                {
                    cout << "ERROR" << endl;
                    break;
                }
                }
            } while (c != 5);
            break;
        }
        case 2: (c1 == 2);
        {
            b.EnterPrint();
            cout << endl;
            cout << "1. Addition" << endl;
            cout << "2. Substraction" << endl;
            cout << "3. Multiplication" << endl;
            cout << "4. Division" << endl;
            cout << "5. exit" << endl;
            do {
                cin >> c2;
                switch (c2)
                {
                case 1: (c2 == 1);
                {
                    b.AddM1();
                    break;
                }
                case 2: (c2 == 2);
                {
                    b.SubM1();
                    break;
                }
                case 3: (c2 == 3);
                {
                    b.MulM1();
                    break;
                }
                case 4: (c2 == 4);
                {
                    b.DivM1();
                    break;
                }
                case 5: (c2 == 5);
                {
                    b.DeleteM;
                    break;
                }
                default:
                {
                    cout << "ERROR" << endl;
                    break;
                }
                }
            } while (c2 != 5);
            break;
        }
        case 3: (c1 == 3);
        {
            cout << "Ex" << endl;
            break;
        }
        default:
        {
            cout << "ERROR" << endl;
            break;
        }
        }
    } while (c1 != 3);
    return 0;
}
