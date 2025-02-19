# Algoritmos-e-Programa-o002-2
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

// 1. Criar cópia do vetor substituindo 0 por 1
void questao1() {
    vector<int> v(5), copia(5);
    cout << "Digite 5 números inteiros: ";
    for (int i = 0; i < 5; i++) {
        cin >> v[i];
        copia[i] = (v[i] == 0) ? 1 : v[i];
    }
    cout << "Vetor original: ";
    for (int num : v) cout << num << " ";
    cout << "\nVetor cópia: ";
    for (int num : copia) cout << num << " ";
    cout << endl;
}

// 2. Mostrar vetor direto ou inverso
void questao2() {
    int codigo, N;
    cout << "Digite o código e o tamanho do vetor: ";
    cin >> codigo >> N;
    if (codigo == 0) return;
    vector<double> v(N);
    cout << "Digite " << N << " números reais: ";
    for (double &num : v) cin >> num;
    if (codigo == 1) for (double num : v) cout << num << " ";
    else if (codigo == 2) for (auto it = v.rbegin(); it != v.rend(); ++it) cout << *it << " ";
    cout << endl;
}

// 3. Encontrar menor e maior elemento e suas posições
void questao3() {
    int N;
    cout << "Digite o tamanho do vetor: ";
    cin >> N;
    vector<int> v(N);
    cout << "Digite " << N << " números inteiros: ";
    for (int &num : v) cin >> num;
    auto minIt = min_element(v.begin(), v.end());
    auto maxIt = max_element(v.begin(), v.end());
    cout << "Menor: " << *minIt << " na posição " << distance(v.begin(), minIt) << endl;
    cout << "Maior: " << *maxIt << " na posição " << distance(v.begin(), maxIt) << endl;
}

// 4. Multiplicação de vetores
void questao4() {
    vector<int> A(5), B(5), C(5);
    cout << "Digite 5 números para o primeiro vetor: ";
    for (int &num : A) cin >> num;
    cout << "Digite 5 números para o segundo vetor: ";
    for (int &num : B) cin >> num;
    for (int i = 0; i < 5; i++) C[i] = A[i] * B[i];
    cout << "Vetor resultante: ";
    for (int num : C) cout << num << " ";
    cout << endl;
}

// 5. Separar positivos e negativos
void questao5() {
    int N, num;
    cout << "Digite o tamanho do vetor: ";
    cin >> N;
    vector<int> positivos, negativos;
    cout << "Digite " << N << " números inteiros: ";
    for (int i = 0; i < N; i++) {
        cin >> num;
        if (num >= 0) positivos.push_back(num);
        else negativos.push_back(num);
    }
    cout << "Positivos: ";
    for (int num : positivos) cout << num << " ";
    cout << "\nNegativos: ";
    for (int num : negativos) cout << num << " ";
    cout << endl;
}

// 6. Troca de elementos entre vetores
void questao6() {
    vector<int> A(6), B(6);
    cout << "Digite 6 números para o vetor A: ";
    for (int &num : A) cin >> num;
    cout << "Digite 6 números para o vetor B: ";
    for (int &num : B) cin >> num;
    for (int i = 0; i < 6; i++) swap(A[i], B[5 - i]);
    cout << "Vetor A após troca: ";
    for (int num : A) cout << num << " ";
    cout << "\nVetor B após troca: ";
    for (int num : B) cout << num << " ";
    cout << endl;
}

// 7. Correção de prova
void questao7() {
    vector<char> G(5), R(5);
    cout << "Digite o gabarito (5 caracteres): ";
    for (char &c : G) cin >> c;
    for (int i = 0; i < 4; i++) {
        cout << "Digite as respostas do aluno " << i + 1 << ": ";
        int acertos = 0;
        for (char &c : R) cin >> c;
        for (int j = 0; j < 5; j++) if (R[j] == G[j]) acertos++;
        cout << "Acertos: " << acertos << " - " << (acertos >= 3 ? "Aprovado" : "Reprovado") << endl;
    }
}

// 8. Interseção de vetores
void questao8() {
    vector<int> A(6), B(6), C;
    cout << "Digite 6 números para o vetor A: ";
    for (int &num : A) cin >> num;
    cout << "Digite 6 números para o vetor B: ";
    for (int &num : B) cin >> num;
    for (int num : A) if (find(B.begin(), B.end(), num) != B.end()) C.push_back(num);
    cout << "Interseção: ";
    for (int num : C) cout << num << " ";
    cout << endl;
}

int main() {
    int escolha;
    do {
        cout << "Escolha uma questão (1 a 8) ou 0 para sair: ";
        cin >> escolha;
        switch (escolha) {
            case 1: questao1(); break;
            case 2: questao2(); break;
            case 3: questao3(); break;
            case 4: questao4(); break;
            case 5: questao5(); break;
            case 6: questao6(); break;
            case 7: questao7(); break;
            case 8: questao8(); break;
        }
    } while (escolha != 0);
    return 0;
}
