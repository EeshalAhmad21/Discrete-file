#include<iostream>
#include<fstream>
#include<sstream>
#include<string>
using namespace std;
struct Edge{
    int src,dest,weight;
};
int main(){
    const int SIZE = 40;  
    string st[SIZE];  
    string f[SIZE][5];  
    Edge edges[SIZE*(SIZE-1)/2];
    int EC=0;
    ifstream in("Friends Dataset.csv");  
    for(int i=0;i<SIZE;i++){
    string line;
    getline(in,line);
    stringstream ss(line); 
    getline(ss,st[i],',');  
    for(int j=0;j<5;j++){
    getline(ss,f[i][j],',');  
}
}
for(int i=0;i<SIZE;i++){
  for(int j =i+1;j<SIZE;j++){
    int CF=0;
    for(int k=0;k<5;k++){
    for(int l=0;l<5;l++){
    if (f[i][k]==f[j][l]){
    CF++;
    }
    }
	 }
    if(CF>0){
    edges[EC++]={i,j,CF};
    }
    }
    }
    for(int i=0;i<EC;i++){
    cout<<st[edges[i].src]<<edges[i].weight<<","<<st[edges[i].dest]<<endl;
    }
    return 0;
}
