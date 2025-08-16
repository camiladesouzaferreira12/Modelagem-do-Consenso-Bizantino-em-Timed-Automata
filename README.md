Este trabalho faz parte de uma proposta de dissertação, e apresenta uma modelagem para o Consenso Bizantino, formalizado por
Leslie Lamport, Robert Shostak, e Marshall Pease. O Consenso Bizantino é  essencial para segurança e funcionamento de sistemas distribuídos,
permitindo que eles operem de forma confiável mesmo na presença de falhas. Para isto, foi utilizado o verificador de modelos UPPAAL, uma
ferramenta que utiliza autômatos temporizados para verificar propriedades críticas em sistemas.

O consenso Bizantino é um problema abstrato onde um grupo de generais do exército bizantino estão acampados com suas tropas ao redor de uma cidade inimiga se
comunicando através de mensageiros. Os generais devem concordar com um plano de batalha, mas alguns deles podem ser traidores que tentarão confundir os outros. O que se
busca é assegurar que os generais leais chegarão a um acordo. Para resolver o problema os generais precisam garantir que: todos os generais leais concordarão e implementarão
o mesmo plano; os generais leais seguirão regras específicas; generais leais devem chegar a um consenso, apesar das ações que os traidores decidem tomar; e generais leais não
seguirão um plano errado sob a influência de generais desleais.

O modelo descrito a seguir é um sistema em UPPAAL que representa o algoritmo OM(f) para solução por mensagem oral do Problema dos Generais Bizantinos com N generais, sendo f traidores.
Assim como na solução dada pelo Algoritmo OM(f) para resolver o Problema dos Generais Bizantinos, nesse sistema fica garantido que todos os generais leais concordem em uma mesma decisão
desde que haja até f traidores. Ele funciona quando há pelo menos 3f + 1 generais. Assim, o comandante envia uma ordem para os tenentes, cada tenente envia a ordem que recebeu do comandante
para os outros tenentes que tomam uma decisão baseada na maioria dos valores recebidos. O termo generais é usado tanto para o comandante, que é o primeiro a enviar uma ordem, quanto para os
tenentes, e o que os diferencia é apenas o momento em que enviam as mensagens, sendo o comandante o primeiro general a enviar uma mensagem e os tenentes os generais que recebem a ordem 
do comandante e em seguida a repassam aos outros, se forem honestos ou, no caso de serem traidores, podem enviar uma ordem diferente da que receberam. No algoritmo de solução por mensagem
oral do problema dos generais bizantinos, a base de recursão é OM(0), usada quando não há traidores, f = 0. Nesse caso o comandante envia sua ordem diretamente para todos os tenentes, que usam a ordem
recebida. Se não recebem nada, assumem a ordem padrão “RETREAT”.
No modelo aqui apresentado, os tenentes sempre recebem alguma ordem do comandante.
