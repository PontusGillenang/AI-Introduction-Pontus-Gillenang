![Assignment](/assets/Assignment.png)

# Arbetsflöde för ett AI-projekt inom husprisförutsägelser

![Workflow](/assets/MachineLearningWorkflow.png)


## Datainsamling
Det går att ladda ner data på [bostadspriser över hela Sverige][4] i excel format som kan omformateras till en csv (Comma-seperated values) fil. Den datan som finns är antal sålda villor, bostadsrätter, fritidshus i olika län, kommuner och hela riket under de senaste månaderna och åren med medelvärdspriset, priset per kvadratmeter och prisutvecklingen i procent.

Den data som samlas in är bland det viktigaste som finns i hela arbetsflödet för om datan som samlats in är dålig kommer också modellen bli dålig då den baserar allt på just denna datan som den tränar, testar och validerar emot.

## Förvaring av data
Den datan som samlats in måste förvaras på ett sätt som gör det möjligt för modellen att utvecklias vidare. Då krävs det en långsiktig förvaring och en hög presterande förmåga för att behandla ny data för senare användning.

Viktiga områden att tänka på när det handlar om dataförvaring är:
- Skalbarhet
- Tillgänglighet
- Fördröjning (latens)
- Genomströmning
- Parallell åtkomst

Vilken dataförvaringslösning som väljs ska det passa för den datatyp som ska hanteras med hänsyn till de listade områdena. Det finns olika molnlösningar från företag som IBM, Microsoft och Google för förvaring och hantering av data men de finns också lokala lösningar beroende på vad som krävs inom de tidigare nämnda områdena.

När datan är insamlad och bearbetad så ska den delas upp så det finns en samling träningsdata, en samling testdata och en samling valideringsdata.
Träningsdatan används för att träna algoritmen för att skapa en modell som utvärderar relationen mellan indatan och utdatan för att kunna se huspris  

## Visualisera data

Det finns flera olika sätt att visa upp data i python men den vi har gått igenom hittills är [Matplotlib][6]. Det är ett bibliotek för att rita upp grafer som till exempel linjediagram och stapeldiagram. Detta kan användas för att se datan visuellt så man kan få en uppfattning av den och se mönster, trender eller sammanhang som man kanske skulle inte ha sätt innan.

## Bearbetning av data

För att kunna bearbeta den insamlade datan så måste den vara i ett format som kan hanteras och importeras in. I detta exempel så finns datan i en Excel fil som kan omformateras till en csv fil. Denna fil ska sedan "städas" upp för att inte innehålla fel och så att man förstår datan så den utdatan man ser är korrekt.

## Linjär regression

Är en "[Supervised Machine Learning Algorithm][1]" vilket betyder att det är en algoritm som använder data som är märkt "labeled" vad det är för indata och utdata.
Den används för att hitta relationen mellan en oberoende variabel (x) och en beroende variabel (y). Detta görs för att förutsäga vad den beroende variabeln (y) blir given en oberoende variabel (x). När det finns fler än en oberoende variabel som indata kallas det för en multipel linjär regression.

### Enkel linjär regressions ekvation
```
y = k * x + m
```
### Mutipel linjär regressions ekvation
```
y(x1,x2,x3) = w1 * x1 + w2 * x2 + w3 * x3 + w0
```

Då det är flera oberoende variablar som ska inverka i förutsägelsen så används mutipel linjär regressions ekvationen.

## Driftsätta modellen

När modellen är tränad, testad och validerad så ska den [driftsättas][9] (deploy to production). Här är det viktigt att man har följt en plan om hur datan samlas in, bearbetas, förvaras och hämtas. För det påverkar hur modellen tränas, testas och valideras för en driftsättning. När modellen driftsätts så är det bra att den sätts in i en "container" som hjälper med skalbarheten, repetivitet och koordinering när modellen går i produktion. När modellen är i produktion ska den konstant övervakas och underhållas så den håller på lång sikt och utför sitt syfte.

## Teknologier

[Python][7] är programmeringsspråket som är mest populärt inom AI, maskininlärning och djupinlärning. I språket finns det olika bibliotek för att [visualisera data][6] som till exempel Matplotlib, Pandas Visualization, Seaborn, plotnine och Plotly.

För att [hantera datan][1] i Python så används bibliotek som till exempel Numpy, Pandas och SciKit Learn.

I driftsättning så är de teknologier som ["containers"][10] som är viktiga för att ha modellen i produktion lokalt eller i molnet.

# Källor

<!-- 

Source
[Linear Regression Machine Learning Project for House Price Prediction][1]

[Predicting House Prices with Linear Regression | Machine Learning from Scratch (Part II)][2]

[The Machine Learning Workflow][3]

[Bostadsstatistik från Sveriges mäklare][4]

[Storage strategies for machine learning and AI workloads][5]

[Introduction to Data Visualization in Python][6]

[5 Best Machine Learning (AI) Programming Languages][7]

[Workflow of a Machine Learning project][8]

[What does it take to deploy ML models in production?][9]

[Use containers to Build, Share and Run your applications][10]

Links
[1]: https://studygyaan.com/data-science-ml/linear-regression-machine-learning-project-for-house-price-prediction

[2]: https://towardsdatascience.com/predicting-house-prices-with-linear-regression-machine-learning-from-scratch-part-ii-47a0238aeac1

[3]: https://learnetutorials.com/machine-learning/machine-learning-workflow

[4]: https://www.maklarstatistik.se/

[5]: https://www.techtarget.com/searchstorage/feature/Storage-strategies-for-machine-learning-and-AI-workloads

[6]: https://gilberttanner.com/blog/introduction-to-data-visualization-inpython/

[7]: https://www.unite.ai/5-best-machine-learning-ai-programming-languages/

[8]: https://towardsdatascience.com/workflow-of-a-machine-learning-project-ec1dba419b94

[9]: https://www.qwak.com/post/what-does-it-take-to-deploy-ml-models-in-production

[10]: https://www.docker.com/resources/what-container/ 

-->

eTutorials, L., 2022. *Machine Learning Workflow | Learn eTutorials.* [online] Learnetutorials.com. Available at: <https://learnetutorials.com/machine-learning/machine-learning-workflow> [Accessed 9 September 2022].

Evans, C., 2022. *Storage strategies for machine learning and AI workloads.* [online] SearchStorage. Available at: <https://www.techtarget.com/searchstorage/feature/Storage-strategies-for-machine-learning-and-AI-workloads> [Accessed 9 September 2022].

Inc., D., 2022. *What is a Container? - Docker.* [online] Docker. Available at: <https://www.docker.com/resources/what-container/> [Accessed 9 September 2022].

Klushin, P., 2022. *What does it take to deploy ML models in production? | Qwak's Blog.* [online] Qwak.com. Available at: <https://www.qwak.com/post/what-does-it-take-to-deploy-ml-models-in-production> [Accessed 9 September 2022].

McFarland, A., 2022. *5 Best Machine Learning (AI) Programming Languages.* [online] Unite.AI. Available at: <https://www.unite.ai/5-best-machine-learning-ai-programming-languages/> [Accessed 9 September 2022].

Mäklarstatistik, S., 2022. *Svensk Mäklarstatistik » Aktuell statistik på bostadspriser i Sverige.* [online] Svensk Mäklarstatistik. Available at: <https://www.maklarstatistik.se/> [Accessed 9 September 2022].

Pant, A., 2022. *Workflow of a Machine Learning Project.* [online] Medium. Available at: <https://towardsdatascience.com/workflow-of-a-machine-learning-project-ec1dba419b94> [Accessed 9 September 2022].

Sayyed, H., 2022. *Linear Regression Machine Learning Project for House Price Prediction - Data Science & ML.* [online] StudyGyaan. Available at: <https://studygyaan.com/data-science-ml/linear-regression-machine-learning-project-for-house-price-prediction> [Accessed 9 September 2022].

Tanner, G., 2022. *Introduction to Data Visualization in Python.* [online] Gilbert Tanner. Available at: <https://gilberttanner.com/blog/introduction-to-data-visualization-inpython/> [Accessed 9 September 2022].

Valkov, V., 2022. *Predicting House Prices with Linear Regression | Machine Learning from Scratch (Part II).* [online] Medium. Available at: <https://towardsdatascience.com/predicting-house-prices-with-linear-regression-machine-learning-from-scratch-part-ii-47a0238aeac1> [Accessed 9 September 2022].