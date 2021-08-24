---
title: Tworzenie kwestionariuszy
description: W tym artykule opisano proces tworzenia kwestionariusza. Pierwszym krokiem jest projektowanie kwestionariusza. Przy projektowaniu kwestionariusza, można nie tylko zapisać pytania i odpowiedzi, ale również utworzyć strukturę, która umożliwia rejestrowanie odpowiedzi i umieszczanie ich w tabelach.
author: andreabichsel
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KCMCollectionType, KMAnswerCollection, KMCollection, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 17341
ms.assetid: b27e2f12-c7a0-4a54-b8d8-17819f8a1c72
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c2a8c156aa75b02b69da3ee70a1ee60ea9d73a8aa67c70babdaaad88d6eb81f4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755571"
---
# <a name="create-questionnaires"></a>Tworzenie kwestionariuszy

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano proces tworzenia kwestionariusza. Pierwszym krokiem jest projektowanie kwestionariusza. Przy projektowaniu kwestionariusza, można nie tylko zapisać pytania i odpowiedzi, ale również utworzyć strukturę, która umożliwia rejestrowanie odpowiedzi i umieszczanie ich w tabelach. 

Starannie zaprojektowany kwestionariusz może pomóc podnieść jakość zbieranych danych. Jeśli dobrze go zaplanujesz, możesz lepiej wybrać odpowiednie opcje w odpowiednim czasie dla kwestionariusza. Następujące porady pomogą Ci zaplanować skuteczny kwestionariusz:

-   Jasno określ cel kwestionariusza, by za pomocą pytań lepiej go zrealizować.
-   Określ osoby lub grupy osób, które będą wypełniały kwestionariusz.
-   Napisz pytania, które znajdą się w kwestionariuszu, i w razie potrzeby uwzględnij opcje kilku odpowiedzi.
-   Upewnij się, że kwestionariusz jest logicznie skonstruowany, aby utrzymać zaangażowanie respondentów.
-   Ułóż pytania i odpowiedzi w kolejności, w jakiej mają być wyświetlane respondentom.
-   W razie potrzeby określ, jak mają być oceniane wyniki.
-   Zdecyduj, czy potrzebne są dodatkowe funkcje. Na przykład można określić, czy i w jaki sposób wyniki powinny być sklasyfikowane, czy wymagany jest limit czasu lub czy wszystkie pytania będą wymagane.

Faza projektowania zawiera cztery kategorie zadań, które należy wykonać w następującej kolejności:

1.  Konfigurowanie wstępnych wymagań, zgodnie z wymaganiami.
2.  Konfigurowanie grupy odpowiedzi i odpowiedzi, jeśli ma zastosowanie.
3.  Konfigurowanie pytań i ich powiązania z grupami odpowiedzi.
4.  Konfigurowanie samego kwestionariusza i dołączanie pytań do niego.

## <a name="prerequisites"></a>Wymagania wstępne
Niektóre warunki wstępne muszą być spełnione przed przystąpieniem do tworzenia kwestionariuszy, pytań i odpowiedzi. Jednak nie wszystkie wymagania wstępne są wymagane w celu uzyskania pełnej funkcjonalności.

### <a name="required"></a>Wymagana

| Wymaganie wstępne        | Opis                |
|---------------------|----------------------------|
| Typy kwestionariuszy | Kategoryzacja kwestionariuszy. |
| Typy pytań      | Kategoryzacja pytań.      |

### <a name="optional"></a>Opcjonalne

| Wymaganie wstępne             | Opis                                                    |
|--------------------------|----------------------------------------------------------------|
| Parametry kwestionariusza | Modyfikowanie podstawowych metod kontroli oraz ustawień domyślnych kwestionariuszy. |

### <a name="questionnaire-types"></a>Typy kwestionariuszy

Typy kwestionariuszy są wymagane i muszą być przypisane podczas tworzenia kwestionariusza. Typy kwestionariuszy pomagają w klasyfikacji kwestionariuszy i zarządzaniu nimi. Do klasyfikacji kwestionariuszy i ich rozróżniania od siebie służą typy kwestionariuszy. Na przykład jeśli masz wiele różnych kwestionariuszy do wyboru, możesz je filtrować według typu w formularzu, co ułatwi znalezienie konkretnego kwestionariusza. Oto kilka przykładów typów kwestionariuszy:

-   Zarządzanie zasobami ludzkimi
-   Ankiety odbiorców
-   Proces przeglądu

### <a name="question-types"></a>Typy pytań

Typy pytań są wymagane i muszą być przypisane podczas tworzenia pytań. 

Typy pytań służą do podziału pytań na kategorie na potrzeby sprawozdawczości. Typy pytań również ułatwiają znajdowanie pytań, ponieważ typy mogą być używane jako filtry na stronie **Pytania**. Oto kilka przykładów typów pytań:

-   Zasoby ludzkie
-   Zarządzanie firmą
-   Ocena kursu

### <a name="questionnaire-parameters"></a>Parametry kwestionariusza

Parametry kwestionariusza są opcjonalne. Nie trzeba ich używać, jeśli firma tego nie wymaga. 

Parametry kwestionariusza definiują anonimowość, kody sekwencji numerów i typy odwołań kwestionariusza. Jeśli organizacja umożliwia dystrybuowanie kwestionariusza, to opcja zachowania anonimowości przez pracowników może być ważna. 

Kody sekwencji numerów służą do organizowania pytań i odpowiedzi. W oparciu o te kody numeracji wartości są automatycznie przypisywane do elementów. 

Wszystkie parametry należy zdefiniować przed rozpoczęciem tworzenia danych. Można zmodyfikować ustawienia parametrów kwestionariusza w dowolnym momencie.

## <a name="questionnaire-components"></a>Składniki kwestionariusza
Kwestionariusze obejmują trzy główne elementy: grupy odpowiedzi zawierające odpowiedzi dla pytań wielokrotnego wyboru, pytania oraz sam kwestionariusz. Opcjonalnie można grupować pytania w kwestionariuszu w grupy wyników. Grupy wyników umożliwiają podziału pytań na kategorie i dostarczania dalszych analiz w kwestionariuszu. 

[![QuestionnaireComponents.](./media/questionnairecomponents-1024x615.png)](./media/questionnairecomponents.png)

### <a name="answer-groups-and-answers"></a>Grupy pytań i odpowiedzi

Respondenci mogą odpowiadać na pytania na dwa sposoby, zależnie od tematu pytania:

-   Pytania otwarte nie wymagają odpowiedzi w określonym formacie. Respondenci wpisać odpowiedź jako tekst, liczbę albo datę lub godzinę. Te pytania zazwyczaj wymagają, aby respondent podał w odpowiedzi informacje subiektywne, takie jak opinia, opis, ocena czy oszacowanie.
-   Pytania zamknięte wymagają, aby respondent wybrał odpowiedź na liście możliwych poprawnych odpowiedzi.

Aby zapewnić listę możliwych odpowiedzi dla pytań zamkniętych, należy utworzyć odpowiedzi w na stronie **Grupy odpowiedzi**. 

Grupy odpowiedzi i odpowiedzi są składnikami, które składają się na główną część informacji, z których tworzone są pytania. Po utworzeniu grupy odpowiedzi można przypisać grupę odpowiedzi do pytania w polu **Grupy pytań** na stronie **Pytania**. 

Grupa odpowiedzi może być następnie używana do jednego lub większej liczby pytań w tym samym kwestionariuszu lub w więcej niż jednym kwestionariuszu. 

> [!NOTE]
> Jeśli modyfikujesz tekst odpowiedzi w grupach odpowiedzi już użytych w wypełnionych kwestionariuszach, dane mogą stać się trudne do oceny i wyniki kwestionariusza przestaną być prawidłowe. Jeśli trzeba zmienić grupy odpowiedzi, należy wziąć pod uwagę utworzenie nowej grupy odpowiedzi zamiast zmieniać istniejące. Nie można usunąć grup odpowiedzi dołączonych do pytania lub odpowiedzi albo tych, które zostały wykorzystane.

### <a name="questions"></a>Pytania

Kwestionariusz musi zawierać pytania. Pytania mogą mieć postać otwartą lub zamkniętą.

-   Odpowiedzi na pytania otwarte nie są kontrolowane i respondenci mogą wpisywać własne odpowiedzi.
-   Pytania zamknięte wymagają listy opcji odpowiedzi i pytania mogą mieć strukturę, aby pozwalać respondentom na wybranie wielu odpowiedzi. Pytania powinny być sformułowane tak, aby uzyskać od respondenta określoną informację i muszą być połączone z grupą odpowiedzi, która zapewnia opcje odpowiedzi dla poszczególnych pytań zamkniętych. 

    > [!NOTE]
    > Przed skonfigurowaniem pytań zamkniętych, należy utworzyć odpowiedzi i grup odpowiedzi.

Pytania mogą zostać ułożone w hierarchii pytań warunkowych, dzięki czemu zadawanie pytań pomocniczych zależy od odpowiedzi, które respondent wybiera do poprzedniego pytania. Można najpierw zapisać pytania i rozmieść je w hierarchii później.

## <a name="setting-up-questionnaires"></a>Konfigurowanie kwestionariuszy

> [!NOTE]
> Przed skonfigurowaniem kwestionariusza, należy skonfigurować odpowiedzi, pytania i wymagania wstępne. 

Dla każdego kwestionariusza można określić następujące informacje:

-   Łączny czas lub limit czasu odpowiedzi na pytania obowiązkowe.
-   Czy wszystkie pytania są obowiązkowe.
-   Czy mają być obliczane punkty na kwestionariuszu.
-   Sposób klasyfikacji wyników.
-   Czy kwestionariusz ma być dostępny dla ograniczonej grupy respondentów.
-   Czy szablon formularza powinien być wyświetlany jako tło każdej strony kwestionariusza.
-   Czy dodatkowe notatki objaśniające respondentowi cele kwestionariusza są wymagane.
-   Czy pytania mają być wyświetlane w ustalonej kolejności lub losowo, czy też wybierane z puli.
-   Czy pytania mają być wyświetlane, tylko jeśli określone odpowiedzi są udzielane w poprzednich pytaniach.

### <a name="set-up-a-questionnaire"></a>Konfigurowanie kwestionariusza

Podstawowa strona, której można użyć do konfiguracji kwestionariusza, to strona **Kwestionariusze**. Aby skonfigurować kwestionariusz, należy wykonać następujące zadania w kolejności:

1.  Tworzenie kwestionariusza.
2.  Wykonaj jedną z następujących czynności dotyczących dołączania pytań do kwestionariusza:
    -   Jeśli używasz grupy wyników, pytania do kwestionariusza można dołączać za pomocą grupy wyników. Najpierw należy zdefiniować grupy wyników kwestionariusza, a następnie dodać do grupy wyników pytania.
    -   Jeśli nie używasz grupy wyników, pytania do kwestionariusza można dołączać bezpośrednio za pomocą kwestionariusza.

3.  Konfigurowanie hierarchii pytań warunkowych, jeśli jest wymagane.
4.  Testowanie kwestionariusza.

Na stronie **Kwestionariusze** kliknij **Sprawdź**, aby sprawdzić poprawność budowy kwestionariusza. Dobrze jest jednak wypełnić kwestionariusz i przetestować go samodzielnie przed rozesłaniem.

### <a name="modify-a-questionnaire"></a>Modyfikowanie kwestionariusza

Na stronie **Kwestionariusze**, możesz wykonać następujące zadania:

-   Modyfikowanie informacji, takich jak grupy wyników i pytania.
-   Usuwanie i dodawanie pytań.
-   Wprowadzanie zmian w grupach wyników i numerach sekwencyjnych 

> [!CAUTION]
> Wprowadzając zmiany do kwestionariuszy, na które udzielono już odpowiedzi, należy zachować ostrożność. Zmiany mogą zmniejszać dokładność danych statystycznych stanowiących w rezultacie wadliwą podstawę do oceny. Zamiast zmieniać pytanie, na które już udzielono odpowiedzi, lepiej rozważyć utworzenie nowego pytania.

Nie można usunąć z kwestionariusza następujących typów pytań:

-   Pytania dołączone do kwestionariusza
-   Pytania, na które udzielono już odpowiedzi, w związku z czym są widoczne w oknie dialogowym **Odpowiedzi**.

### <a name="result-groups"></a>Grupy wyników

Grupy wyników są opcjonalne podczas dołączania pytań do kwestionariusza. 

Grupa wyników jest używana do obliczania punktów i klasyfikacji wyników kwestionariusza. Korzystając z grup wyników, można wykonywać następujące zadania:

-   Ocena wyników kwestionariusza na podstawie statystyki punktów.
-   Ocena punktacji respondenta dla poszczególnych ustawionych grup wyników.
-   Generowanie statystyk poszczególnych grup wyników ułatwiające analizowanie wyników.
-   Drukowanie raportu, który pokazuje wyniki dla każdej grupy wyników, a także opcjonalne punkty/teksty, oparte na punktach przyznawanych w każdej grupie wyników.

> [!NOTE]
> Przed skonfigurowaniem grup wyników, należy wykonać następujące zadania:

-   Konfigurowanie pytań zamkniętych. Dla pytań zamkniętych należy danymi wejściowymi na stronie **Pytania** strona musi być **Pole wyboru**, **Alternatywny przycisk** lub **Pole kombi**.
-   Zdefiniuj punkty za odpowiedzi w grupie odpowiedzi przypisanej do każdego pytania.
-   Konfigurowanie kwestionariusza.

Aby dołączyć pytania do kwestionariusza, korzystając z grup wyników, najpierw należy zdefiniować grupy wyników kwestionariusza, a następnie dodać do grupy wyników pytania. Jeśli nie używasz grupy wyników, pytania do kwestionariusza można dołączać bezpośrednio za pomocą kwestionariusza. 

Można skonfigurować wiele grup wyników do oceny punktacji, które respondent uzyskuje w każdej kategorii. Po wypełnieniu kwestionariusza, można wyświetlić punkty uzyskane dla każdej grupy wyników. 

> [!TIP]
> Do oceny kwestionariusza za pomocą punktów, ale nie oddzielnych kategorii, wszystkie pytania można dodać do jednej grupy wyników. 

Dla każdej grupy wyników można skonfigurować co najmniej jedną wiadomość opartą na punktach, którą respondenci otrzymują po wypełnieniu kwestionariusza. Wyświetlany tekst może być różny w zależności od wyniku uzyskanego przez respondenta w grupie wyników. Aby używać wiadomości opartych na puntach, trzeba zdefiniować przedziały punktacji i opisy do każdego z przedziałów. Gdy respondent osiąga wynik z określonego przedziału, do raportu wyników jest dołączany tekst przeznaczony dla tego przedziału. 

Ponieważ grupy wyników są powiązane z punktami, które są skojarzone z określonymi zestawami pytań w kwestionariuszu, w kwestionariuszu można używać tylko określonej grupy wyników.

#### <a name="example-pointstexts-for-result-group-3"></a>Przykład: Punkty/teksty dla grupy wyników 3

Używasz kwestionariusza do sprawdzania zdolności przywódczych, który ma 15 pytań w trzech kategoriach. Można utworzyć trzy grupy wyników i dodać pięć pytań do każdej grupy wyników. Następnie punkty są sumowane w trzech grupach. Trzy grupy wyników są następujące:

-   Zdolności twórcze
-   Zdolności przywódcze
-   Zdolności techniczne

Aby użyć wiadomości opartych na punktacji, konfigurujesz interwały tekstu dla każdego grupy wyników. Każde pytanie jest przypisane do dwóch punktów. Dlatego maksymalna ilość punktów w każdej z grup wyników wynosi 10. 

W poniższej tabeli przedstawiono komunikaty na podstawie punktów zdefiniowane dla grupy wyników „Zdolności przywódcze”.

| Przedział punktów | Tekst                                       |
|----------------|--------------------------------------------|
| 1 do 3         | Masz średnie zdolności przywódcze.     |
| 4 do 7         | Masz dobre zdolności przywódcze.        |
| 8 do 10        | Masz nieprzeciętne zdolności przywódcze. |

Można skonfigurować przedziały punktacji i tekstów dla poszczególnych grup wyników kwestionariusza. Teksty, które odpowiadają wynikom respondentów są wyświetlane dla każdej grupy wyników. 

> [!NOTE]
> Przedziały i tekst można zmieniać. Jednak jeśli kwestionariusz został ukończony, zmiany mogą wywołać niezgodności między starymi i nowymi raportami wyników.

### <a name="conditional-question-hierarchies"></a>Hierarchie pytań warunkowych

Hierarchie pytań warunkowych są opcjonalne podczas ustawiania kwestionariusza. 

> [!NOTE]
> Przed utworzeniem hierarchii pytań warunkowych należy dołączyć do kwestionariusza pytania, do których przypisane są grupy odpowiedzi. 

Aby używać pytań warunkowych to utworzenie hierarchii pytań w kwestionariuszu, można utworzyć kolejność prezentowania pytań w zależności od odpowiedzi wybranej w każdym pytaniu. Opierając sekwencję pytań na odpowiedziach respondenta, można modyfikować kwestionariusz do respondenta, który go wypełnia.

#### <a name="examples"></a>Przykłady

Firma oferuje klientom towary i usługi. Zwykle w takich przypadkach niektórzy klienci kupują tylko towary, inni tylko usługi, a jeszcze jedni towary i usługi. Dlatego gdy firma rozsyła ankietę badania poziomu zadowolenia klientów, wprowadza do kwestionariusza strukturę warunkową, aby klienci, którzy nabywają same usługi, nie musieli odpowiadać na pytania dotyczące towarów. 

Alternatywnie można ustawić kwestionariusz tak, że jeśli respondent wybierz odpowiedź A na pytanie 1, następnym pytaniem w sekwencji jest pytanie 2. Jeśli jednak respondent wybierze odpowiedź B na pytanie 1, następnym pytaniem jest pytanie 5.

[!INCLUDE[footer-include](../includes/footer-banner.md)]