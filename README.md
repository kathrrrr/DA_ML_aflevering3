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
Konklusion: Efter at have afsøgt forskellige fremgangsmåder til forbedring af modellens præcision (accuracy score), kan vi se at scoren for det beskårede træ er 60.7%, hvilket er noget bedre end ved det oprindelige træ, hvor den var 56.7%
Vi får altså den bedste score ved at bruge Giniindexet, og da træ med entropy der beskæres var bedre en ved logistisk regression, så er dette træ med Gini, beskåret endnu bedre.

Fil: deep_learning_classification.ipynb
Her har vi lavet iterative gennemløb af dataen med ANN (artificial neural network), sekventiel model, regularisering vha dropout-lag samt tuning af hyperparametre og holdt det op imod accuracy score med henblik på at finde den optimale kombination. 
Konklusion: Overordnet kan vi konkludere, at tensorboardet giver et godt overblik over epochs og loss. Det bliver tydeligt hvornår både epochs og loss begynder og flader ud, og hvor der evt. kunne være brug for et early stop. Tensorboardet gir også et indtryk, i graferne for epochs vs. iteration og loss vs. iteration, af over og under fitting.  
Ud fra tre gennemløb af vores test af modellen kan vi også i denne version konkludere følgende med nogenlunde sikkerhed:  
  * Det betyder rigtig meget for modellens accuracy, hvordan den er sat sammen (vi får i dette tilfælde resultater fra ca. 49% til ca 66%).  
  * Vi kan efter de tre gennemløb se, at vi overvejende får et godt resultat ved at bruge rmsprop optimeringsmetoden. Vi kan anvende sgd og adam, men det kræver et stort antal neuroner og mange epochs.  
  * Vi skal undgå at bruge sgd optimeringsmetoden sammen med lavt epochs og lavt neuron tal, da dette vil resultere i lav score.  
Vi svært ved at sige noget om:  
  * Når vi anvender rmsprop som optimering, er det svært at finde mønster i epochs og dropout.
Det ser ud til at være mest fornuftigt at bruge rmsprop, når man som i vores tilfælde bruger ANN og kun et lag. Det ser også, ikke uventet, ud til at et stort antal neuroner samt et rimeligt antal dropouts gir det bedste resultat. Se evt. de vedhæftede oversigtsbilleder med 'worst' og 'best', der viser de værste/bedste optimeringsmetoder.  
