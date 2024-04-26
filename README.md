# DA_ML_aflevering3
Dataanalyse og Machine Learning (F24.520214U002.A)
Gruppe 1:
Hans Christian Hulvej - AU19930532
Kathrine Bohus Madsen - AU202301227
Tor Kolding - AU20000148
Torben Holst Rendboe – AU20064217

I denne ReadMe fil har vi valgt at lave en kort oversigt over de forskellige dokumenter i aflevering 3 samt en opsamlende konklusion.
I alle dele af arbejdet har vi anvendt datasettet WineQT.csv 

Fil: random_forest_classification.ipynb
Her har vi arbejdet med klassifikationstræer, beslutningstræer, bagging, tuning af hyperparametre samt krydsvalidering (k-fold og leave one out)
Konklusion: Vi kan på baggrund af ovenstående beregninger og analyser konkludere flg. med nogenlunde sikkerhed:
* Standardscoren for klassifikation med Random Forest Classification fra Scikit Learn kan forbedres ved tuning af parameteren.
* En grådig tuning af parametrene forbedrer standardscoren.
* En randomiseret test af parameterkombinationer giver en lidt højere score.
* Den største effekt opnås ved at bruge Leave One Out krydsvalidering.

Fil: Klassifikationstræ
Ligesom i den foregående fil forsøger vi her at anvende et klassifikationstræ på wineQT.csv datasættet med anvendelse af Entropy og Giniindex. Vi forsøger at skrue på træets dybde ved at beskære det (prunning) for at opnå en højere accuracy for modellen.
Konklusion:
Med entropy er scoren for det beskårede træ 60.1%, hvilket er noget bedre end ved det oprindelige træ, hvor den kun havde en score på 55.3% Den er også bedre end de 
57.3% ved logistisk regression, som vi lavede i aflevering 2.
Med Giniindex er scoren for det beskårede træ 60.7%, hvilket er en anelse bedre. Vi får altså den bedste score ved at bruge Giniindexet, og da træ med entropy der beskæres var bedre end ved logistisk regression, så er dette træ med Gini, beskåret endnu bedre. 

Fil: Deep_learning_classification_tensorflow_tenserboard
Her har vi lavet iterative gennemløb af dataen med ANN (artificial neural network) og inddraget forskellige metoder og skruet på parametre for at forbedre accuracy score med henblik på at finde den optimale kombination. 
Konklusion: 
Overordnet kan vi konkludere, at tensorboardet giver et godt overblik over epochs og loss. Det bliver tydeligt hvornår både epochs og loss begynder og flader ud, og hvor der evt. kunne være brug for et early stop. Tensorboardet gir også et indtryk, i graferne for epochs vs. iteration og loss vs. iteration, af over/under fitting.  
Ud fra tre gennemløb af vores test af modellen kan vi også i denne version konkludere følgende med nogenlunde sikkerhed:  
* Det betyder rigtig meget for modellens accuracy, hvordan den er sat sammen (vi får i dette tilfælde resultater fra ca. 49% til ca 66%).  
* Vi kan efter de tre gennemløb se, at vi overvejende får et godt resultat ved at bruge rmsprop optimeringsmetoden. Vi kan anvende sgd og adam, men det kræver et stort antal neuroner og mange epochs.  
* Vi skal undgå at bruge sgd optimeringsmetoden sammen med lavt epochs og lavt neuron tal, da dette vil resultere i lav score.  
Vi svært ved at sige noget om:  
* Når vi anvender rmsprop som optimering, er det svært at finde mønster i epochs og dropout.
Det ser ud til at være mest fornuftigt at bruge rmsprop, når man som i vores tilfælde bruger ANN og kun et lag. Det ser også, ikke uventet, ud til at et stort antal neuroner samt et rimeligt antal dropouts gir det bedste resultat. Se evt. de vedhæftede oversigtsbilleder med 'worst' og 'best', der viser de værste/bedste optimeringsmetoder.

Fil: deep_learning_classification.ipynb 
Denne fil minder om den foregående, dog med lidt færre delelementer, hvor målet har været at opbygge et neuralt netværk med Tensorflow og Keras til klassifikation af vinene i vindatasættet. Igen har målet været at opnå en højere accuracy ved at skrue på forskellige parametre i den sekventielle model, inddrage regularisering vha dropout-lag samt tuning af hyperparametre. 
Konklusion: 
Ud fra vores test af modellen kan vi konkludere følgende med nogenlunde sikkerhed:
* Det betyder rigtig meget for modellens accuracy, hvordan den er sat sammen (vi får resultater fra ca. 40% til ca 64%).
* Vi har ikke fundet en kombination, som kan måle sig med den bedste af de mere simple metoder (se random forests filen)
Vi kan ikke sige meget om:
* Kunne vi sammensætte en model, som præsterer endnu bedre?
* Er det de mest relevante parametre, vi har ændret på?



