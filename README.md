# Problem-Solving

string gridSearch(vector<string> G, vector<string> P) {
    char k=P[0][0];
    string s1="YES",s2="NO";;
    int i,j,l,m;
    for( i=0;i<G.size()-P.size()+1;i++){
        for(j=0;j<G[0].size()-P[0].size()+1;j++){
            int cnt=0;
            if(G[i][j]==k){
                for( l=i;l<i+P.size();l++){
                    for( m=j;m<j+P[0].size();m++){
                        if(G[l][m]!=P[l-i][m-j]){
                            cnt=1;
                            break; 
                        }
                    }
                    if(cnt==1){
                        break;
                    }
                }
            }
            if(l==i+P.size() && m==j+P[0].size()){
                break;
            } 
        }
        if(l==i+P.size() && m==j+P[0].size()){
                break;
            }
    }
    if(l==i+P.size() && m==j+P[0].size()){
      return s1;
    }
    else{
      return s2;
    }
}
