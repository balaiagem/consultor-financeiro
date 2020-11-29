quantia_poupada(21000).
ganhos(25000, estavel).
dependentes(3).

poupanca_min(K, Y):- K is Y * 5000.
conta_poupanca(adequada):- quantia_poupada(X), dependentes(Y), poupanca_min(K, Y), X > K.
conta_poupanca(inadequada):- quantia_poupada(X), dependentes(Y), poupanca_min(K, Y), X < K.

renda_min(K, Y):- K is Y * 5000 + (4000 * Y).
renda(adequada):- ganhos(X, estavel), dependentes(Y), renda_min(K, Y), X > K.
renda(inadequada):- ganhos(X, estavel), dependentes(Y), renda_min(K, Y), X < K.

investimentos(poupanca):- conta_poupanca(inadequada).
investimentos(acoes):- conta_poupanca(adequada), renda(adequada).
investimentos(combinacao):- conta_poupanca(adequada), renda(inadequada).
investimos(tesouro direto):- conta_poupanca(inadequada),renda(adequada).
investimos(fii):- conta_poupanca(adequada),renda(adequada).
investimentos(imoveis):- conta_poupanca(adequada),renda(inadequada).
