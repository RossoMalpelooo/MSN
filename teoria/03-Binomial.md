Dall'ultima lezione sul modello di Ehrenfest si era arrivati alla conclusione che la probabilità di trovare $n$ biglie nell'urna di riferimento (ed $N-n$ nell'altra) ad un tempo $t$ significativo (ovvero che tende a $\infty$) è descritta da una [_distribuzione binomiale_](https://it.wikipedia.org/wiki/Distribuzione_binomiale). 

Questa tipologia di distribuzione descrive un esperimento di prove ripetute. In particolare, la formula
$$ \mathcal{B}_{N, \,p} (n) = \binom{N}{n} \, p^n(1-p)^{N-n} $$
contiene i parametri:
- $N$ : numero di prove totali;
- $n$ : numero di prove vincenti;
- $p$ : probabilità di successo sulla singola prova.

### Momenti
I _momenti_ principali della distribuzione binomiale sono il _valore atteso_(anche _media/speranza matematica_) e la _varianza_(anche _secondo momento centrato_).

La definizione del valore atteso di una variabile aleatoria è 
$$ \mathbb{E}\left[m\right] = \sum_{i=1}^{\infty} m_i \, p_i $$
Mentre per la varianza vale
$$ \sigma_{m}^2 = \mathbb{E} \left[ (m - \mathbb{E}\left[ m \right])^2 \right] $$
Queste definizioni sono entrambe ricavabili partendo dal [binomio di Newton](https://it.wikipedia.org/wiki/Teorema_binomiale) 
$$ (p+q)^n = \sum_{m=0}^n \binom{n}{m} p^m \, q^{n-m} $$
Il primo passo è quello di derivare una volta rispetto a $p$
$$ n\,(p+q)^{n-1} = \sum_{m=1}^n \binom{n}{m}m\,p^{m-1}q^{n-m} $$
Poi, moltiplicando ambo i membri per $p$
$$ n\,p\,(p+q)^{n-1} = \sum_{m=0}^n \binom{n}{m}m\,p^m q^{n-m} $$
e assegnando $q = 1-p$ e dunque $p+q=1$, si ottiene il risultato che si voleva dimostrare inizialmente
$$ n\,p = \sum_{m=0}^n m\binom{n}{m} \, p^m(1-p)^{n-m} $$
Allo stesso modo, per ricavare la varianza si utilizza la derivata seconda partendo dal binomio 
$$ n\,(n-1)\, \left(p+q\right)^{n-2} = \sum_{m=2}^n \binom{n}{m} m \left(m-1\right) \, p^{m-2} q^{n-m} $$
e si moltiplica per il termine $p^2$ 
$$ n\,(n-1)\,p^2 \, \left(p+q\right)^{n-2} = \sum_{m=2}^n \binom{n}{m} m \left(m-1\right) \, p^m q^{n-m} $$
si aggiunge poi il vincolo $p+q=1$
$$ n\,(n-1)\,p^2 = \sum_{m=0}^n m \left(m-1\right) \, \mathcal{B}_{n,p}(m) = \sum_{m=0}^n m^2\,\mathcal{B}_{n,p}(m) - \sum_{m=0}^n m\,\mathcal{B}_{n,p}(m) $$
$$ n^2p^2 - np^2 = \mathbb{E}\left[m^2\right] - \mathbb{E}\left[m\right] 
= \left(\mathbb{E}\left[m\right]\right)^2 - np^2 = \mathbb{E}\left[m^2\right] - np
$$
da cui 
$$ \sigma_m^2 = \mathbb{E}\left[m^2\right] - \left(\mathbb{E}\left[m\right]\right)^2 = np - np^2 = n\,p\,(1-p) $$




