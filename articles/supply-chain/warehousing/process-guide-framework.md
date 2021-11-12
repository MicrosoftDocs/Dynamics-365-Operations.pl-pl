---
title: Struktura przewodnika procesu
description: Ten temat zawiera informacje dotyczące struktury przewodnika po procesach dla programistów rozszerzających nasze procesy mobilne magazynu w języku X++.
author: MarkusFogelberg
ms.date: 11/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: ecf4bf884bca80cabb066ae43d38cd9c0e159216
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2021
ms.locfileid: "7652066"
---
# <a name="process-guide-framework"></a>Struktura przewodnika procesu

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje dotyczące struktury przewodnika po procesach dla programistów rozszerzających procesy mobilne magazynu w języku X++. Procesy mobilne magazynu mogą być rozszerzalne w wyniku podziału procesów na mniejsze kroki. Logika biznesowa i interfejs użytkownika poszczególnych kroków zostały wyodrębnione do poszczególnych klas, co umożliwia rozszerzanie.

## <a name="overview-of-the-existing-design"></a>Omówienie istniejącego projektu

Przepływy wykonywania mobilnego magazynu są udostępniane za pośrednictwem jednego niestandardowego punktu końcowego usługi. Żądanie pochodzi z aplikacji mobilnej w postaci ciągu XML, który zawiera metadane interfejsu użytkownika prezentowane w aplikacji mobilnej, a także wartości wprowadzone przez użytkownika.

Gdy żądanie zostanie odebrane, pierwszym krokiem jest deserializowanie tego kodu XML. Klasa **WHSMobileAppServiceXMLTranslator** konwertuje kod XML na kontener, który zawiera zarówno informacje o kontroli, jak i informacje o sesji.

Poniżej przedstawiono informacje zawarte w kontenerze, które służą do odliczenia procesu magazynowego, nad którym pracuje lub zacznie pracować użytkownik(reprezentowane przez wyliczenie **WHSWorkExecuteMode**) i odpowiednio utworzenia wystąpienia klasy pochodnej **WHSWorkExecuteDisplay**. Zostanie wywołana metoda **displayform()**, która następnie powoduje:

-   Przetwarzanie danych użytkownika (delegowane do klasy **WHSRFControlData**, ale niektóre procesy implementują określoną logikę, zastępując metodę **processControl()**). 

-   Wykonane logiki biznesowej.

-   Zwiększanie kroku.

-   Tworzenie kontenera reprezentującego nowy interfejs użytkownika (zazwyczaj w metodzie **build…()**).

Następnie kontener zostanie zwrócony tłumaczowi, który serializuje kod XML i wysyła go z powrotem jako odpowiedź na urządzenie przenośne.

Na poniższym diagramie kolejności przedstawiono omówienie przepływu wykonania. Należy zauważyć, że diagram jest tylko schematycznym omówienie, a nie dosłownym przedstawieniem rzeczywistego kodu.

![Schematyczne omówienie procesu.](media/schematic-overview.png) 

### <a name="reason-for-the-redesign"></a>Przyczyna ponownego projektu

Powyższy projekt oferuje bardzo proste struktury procesów kompilacji używanych w przepływach mobilnych. Jednak jak widać powyżej, metody **displayform()** przejmą wiele odpowiedzialności. Deleguje je to do innych metod i klas, ale przy braku konkretnych odpowiedzialności klasy jest to niespójnie wykonywane w różnych klasach. Ponadto ze względu na wzrost liczby obsługiwanych scenariuszy niektóre z tych klas mogą stać się dosyć złożone. Co ciekawe, niektóre z tych klas/metod są zastępowe i używane ponownie w wielu trybach. Wynikiem są bardzo długie metody o wysokiej cyklicznej złożoności. W przeszłości powodowały one problemy podczas konserwacji. Poprawianie błędów w tych metodach jest ryzykowne i może powodować regresję.
Na przykład metoda **processWorkLine()** w klasie **WhsWorkExecuteDisplay** odnosi się do wielu procesów (zasadniczo w każdym miejscu wykonywania pracy).

Aby te metody były rozszerzalne, jedną z opcji może być podzielenie metod **displayForm** na mniejsze i wprowadzenie punktów możliwości rozszerzania. Jednak ze względu na matrycę scenariuszy trudne byłoby dla partnerów pisanie rozszerzeń i weryfikowanie ich pod względem regresji. Poza tym z powodu braku wymienionej powyżej struktury podziału obowiązku kod będzie nadal się z czasem rozrastał w nieprzewidywalny sposób, powodując trudności w kompilacji wysokiej jakości rozszerzeń.

W związku z tym przeprojektowanie jest stabilną opcją, co ma wyraźnie zdefiniować klasy mające niezależne obowiązki. Klasa powinna mieć jeden obowiązek, jedną przyczynę zmiany i jedną przyczynę rozszerzenia.

## <a name="design-overview"></a>Omówienie projektu

W przeprojektowanej strukturze podstawowa strategia bazuje na dwóch zasadach: dziel przepływ wykonywania na poszczególne składniki z jasno zdefiniowanymi obowiązkami i pamiętaj o dobrze zdefiniowanych punktach rozszerzeń w każdym z tych składników.

Nazwa nowej struktury to „ProcessGuide”. Wynika to z tego, że celem tych klas jest przeprowadzenie użytkownika przez proces biznesowy (w przeciwieństwie do rozbudowanego klienta, czyli doświadczeń opartych na formularzach, w których użytkownik ma większą elastyczność sposobu interakcji z danymi lub kolejności wykonywania zadań).

> [!NOTE]
> Szczególną uwagę zwraca celowe pominięcie prefiksu „WHS”. Chociaż procesy mobilne zostały początkowo wprowadzone do magazynu, w dalszej kolejności przekroczyły one granice w celu obsługi różnych procesów zarządzania produkcją i zapasami. W związku z tym odwołanie do magazynu zostało wykluczone z nazwy struktury.

Aby zidentyfikować składniki, pierwszym krokiem jest uruchomienie procesu produkcji (klasa **WhsWorkExecuteDisplayProdStart**). Poniżej znajduje się schemat procesu.

![Obraz schematycznego procesu.](media/production-start-process-schematic.png)

Następujące składniki są wymagane pod kątem przepływu sterowania:

-   Kontroler na potrzeby zszycia całego procesu biznesowego.
-   Krok odpowiedzialny za wykonanie kroku w procesie.
-   Procesor danych do przetwarzania danych w kroku.
-   Konstruktor stron odpowiedzialny za tworzenie interfejsu użytkownika dla kroku.
-   Agent nawigacji odpowiedzialny za przejście do kroku.
-   Klasa odpowiedzialna za wykonywanie procesu biznesowego.

Jeśli powyższy diagram przepływu procesu rozpocznie się w kroku 1 i rozpocznie przetwarzanie danych z poprzedniego kroku, a następnie zakończy się tworzeniem interfejsu użytkownika, dane będą nadal przetwarzane w następnym kroku. Wprowadza to ścisły związek między kolejnymi krokami, dzięki temu nowy schemat wysokiego poziomu będzie wyglądać następująco:

![Obraz schematycznego procesu wysokiego poziomu.](media/high-level-schematic.png)

Poniżej przedstawiono najważniejsze składniki procesu przeprojektowania:

-   **ProcessGuideController** — ta klasa organizuje ogólne wykonywanie procesu biznesowego. Definiuje ona współczynniki, które utworzą wystąpienie kroku i agenta nawigacji, które stanowią następnie wykonanie procesu, a także logikę oczyszczania dla anulowania lub zakończenia procesu.

-   **ProcessGuideStep** — ta klasa reprezentuje jeden krok w procesie biznesowym. Ta klasa zawiera definicję współczynników, które inicjują wystąpienie konstruktora stron, akcje i procesory danych oraz są odpowiedzialne za ich wywołania w prawidłowej kolejności.

-   **ProcessGuideNavigationAgent** — ta klasa jest odpowiedzialna za nawigację między krokami. Po zakończeniu kroku agent nawigacji jest odpowiedzialny za zdefiniowanie następnego kroku i przechodzi wszystkie parametry, których poprzedni krok może wymagać do komunikowania się z następnym krokiem.

-   **ProcessGuidePageBuilder**— ta klasa jest odpowiedzialna za inicjowanie wystąpienia interfejsu użytkownika.

-   **ProcessGuideAction** — ta klasa reprezentuje akcję, pokazywaną jako przycisk dla użytkownika.

-   **ProcessGuideDataProcessor** — ta klasa jest odpowiedzialna za przetwarzanie danych wprowadzonych w polu przez użytkownika.

## <a name="execution-flow"></a>Przepływ wykonania

Punkt początkowy przepływu wykonywania pozostaje niezmieniony. Żądanie nadal będzie docierać do tych samych punktów końcowych, po czym następuje deserializacja kodu XML do kontenera. Ten kontener jest następnie przekazywany do **getNextFormState()**.

Istnieją trzy ważne klasy, o których należy pamiętać:

-  **ProcessGuideSessionState** — zawiera informacje o stanie sesji — tryb, przekazanie, kontroler i krok, który jest wykonywany, itp.

-  **ProcessGuidePage** — zawiera zdecydowanie wpisaną reprezentację metadanych interfejsu użytkownika.

-  **ProcessGuideRequest** — zawiera wymienione powyżej dwa elementy i jest to zdecydowanie wpisana reprezentacja żądania odebranego z urządzenia przenośnego.

Te klasy są tworzone przy użyciu informacji o kontenerze (dane kontroli wprowadzone zarówno dla stanu, jak i użytkownika). Zapewnia to bezpieczny sposób uzyskiwania dostępu do wartości i manipulowania nimi. W porównaniu z wielokrotnym dostępem do kontenera w trakcie procesu zapewnia to korzyści zarówno pod względem czytelności, jak i wydajności.

Informacje o stanie sesji służą do tworzenia wystąpienia poprawnej klasy **ProcessGuideController**. Po utworzeniu wystąpienia wywołano metodę **createResponse()** w klasie **ProcessGuideController**. Ta metoda jest punktem wejścia logiki przewodnika po procesie, a po wykonaniu jest wróci z odpowiedzią (reprezentowaną w klasie **ProcessGuideResponse**). Odpowiedź jest następnie konwertowana z powrotem do kontenera i odsyłana do starszej logiki, która następnie serializuje ją w formacie XML i wysyła odpowiedź z powrotem do urządzenia przenośnego.

Następnie kontroler musi znaleźć następny krok do wykonania. Jeśli jest to początek nowego procesu, kontroler wywoła **initialStep()** w celu uzyskania pierwszego kroku w procesie. Następnie może wywołać metodę **execute()** w **ProcessGuideStep**. Ta metoda powinna następnie utworzyć wystąpienie klasy **ProcessGuidePageBuilder** i wywołać metodę **buildPage()**, która zwracałaby obiekt **ProcessGuidePage**, będący wirtualną reprezentacją interfejsu użytkownika prezentowaną użytkownikowi. Następnie krok wysyła wynik z powrotem do kontrolera, co spowoduje zapisanie bieżącego stanu sesji, a następnie zwrócenie wyniku do stanu **getNextFormState()** w formie klasy **ProcessGuideResponse**. Następnie odpowiedź jest konwertowana z powrotem do kontenera, a następnie serializowana na format XML i wysyła odpowiedź z powrotem na urządzenie przenośne.

Poniższy diagram sekwencji przedstawia ten przepływ sterowania. Należy zauważyć, że jest to najczęściej występujący przepływ sterowania, uproszczony w celu wyjaśniania projektu.

![Uproszczony przepływ sterowania.](media/control-flow.png)

Gdy użytkownik podejmuje akcję na urządzeniu przenośnym, klikając przycisk (lub skanując wartość, co zazwyczaj wyzwala akcję domyślną) — żądanie dociera do metody **createResponse()** w klasie **ProcessGuideController** za pośrednictwem tej samej marszruty. Jednak tym razem kontroler ma informacje dotyczące stanu sesji, więc wie, na którym etapie znajduje się użytkownik. W związku z tym tworzy wystąpienie odpowiedniej klasy **ProcessGuideStep** i wywołuje metodę wykonania. Z kolei **ProcessGuideStep** odczytuje nazwę akcji wywołaną przez użytkownika, a następnie tworzy wystąpienie odpowiedniej klasy **ProcessGuideAction** i wywołuje działanie **execute()**.

Klasa **ProcessGuideAction** jest odpowiedzialna za wykonywanie określonej akcji, jednak występują dwa ważne wyjątki.

Pierwszym z nich jest klasa **ProcessGuideOKAction**. W tej akcji zakłada się, że użytkownik chce potwierdzić tę czynność i przejść dalej w procesie. Zgodnie z tym — ta metoda w rzeczywistości nie wykonuje wywołania zwrotnego do klasy ProcessGuideStep, co oznacza, że krok wywołuje metodę **processData()** w **ProcessGuideDataProcessor**. Spowoduje to przetwarzanie danych wprowadzonych przez użytkownika, a następnie aktualizuje stan kroku i wysyła wynik z powrotem do kontrolera. W zależności od wyniku procesora krok wywoła konstruktora stron w celu skompilowania odpowiedniego interfejsu użytkownika lub ustawienie stanu kroku jako zakończonego. Znajduje się on w górnej części diagramu sekwencji poniżej.

Innym wyjątkiem jest akcja anulowania, zaimplementowana w klasach **ProcessGuideCancelResetProcessAction** i **ProcessGuideCancelExitProcessAction**. Te akcje reprezentują zamiar anulowania procesu i powrotu do jego rozpoczęcia lub całkowitego jego opuszczenia. Podobnie jak akcja **OK**, akcje te wykonują również wywołanie zwrotne do kroku, co wysyła sygnał do **ProcessGuideController**. Kontroler wykonuje wówczas niezbędne oczyszczanie zmiennych stanu i przenosi kontrolę do początkowego kroku w procesie albo całkowicie kończy proces.

Po zakończeniu kroku, jeśli stan kroku jest ustawiony na **Zakończono**, kontroler tworzy wystąpienie **ProcessGuideNavigationAgent**, które zwraca nazwę następnego kroku. Kontroler następnie tworzy wystąpienie tego kroku i wywołuje metodę **execute()** — i cykl będzie kontynuowany. Najczęściej nowy krok wywołuje odpowiedni **ProcessGuidePageBuilder** w celu skompilowania interfejsu użytkownika dla następnego ekranu, który ma być przedstawiany użytkownikowi, a który jest następnie wysyłany z powrotem. Przepływ jest przedstawiony się on w dolnej części diagramu sekwencji poniżej.

![diagram sekwencji.](media/sequence-diagram.png)

## <a name="building-a-new-process-using-the-processguide-framework"></a>Tworzenie nowego procesu przy użyciu struktury ProcessGuide

Najlepszym sposobem wyjaśnienia przepływu sterowania jest przykład, który istnieje w aplikacji, czyli proces rozpoczęcia produkcji.

## <a name="overview-of-the-production-start-process"></a>Omówienie procesu rozpoczęcia produkcji

Zacznijmy od zrozumienia przepływu procesu. W pierwszym kroku użytkownik jest monitowany o identyfikator zlecenia produkcyjnego.

![Monituj o identyfikator produkcji.](media/production-id-prompt.png)

Po wejściu przez użytkownika do identyfikatora zlecenia produkcyjnego jest sprawdzana poprawność numeru zamówienia. Niektóre uruchamiane sprawdzenia poprawności są oparte na tym, czy zamówienie znajduje się w tym samym magazynie, do którego jest zalogowany użytkownik, oraz na stanie zamówienia. Jeśli sprawdzanie poprawności nie powiedzie się, użytkownikowi będzie wyświetlany komunikat o błędzie. Jeśli sprawdzenie poprawności się powiedzie, użytkownikowi będą wyświetlone szczegóły zlecenia produkcyjnego i pozycji.

Użytkownik może anulować, aby wrócić do rozpoczęcia procesu, lub kliknąć przycisk **OK**, aby potwierdzić. W drugim przypadku zlecenie produkcyjne ma stan **Rozpoczęte**, księgowane są odpowiednie arkusze, kontrola przechodzi do pierwszego etapu, a użytkownikowi jest wyświetlany komunikat „Praca zakończona”.


## <a name="creating-the-controller"></a>Tworzenie kontrolera

Pierwszym krokiem w tworzeniu procesu biznesowego jest utworzenie klasy kontrolera, która rozszerza klasę abstrakcyjną **ProcessGuideController**, która implementuje domyślne zachowania kontrolera. Nową nazwą klasy jest **ProdProcessGuideProductionStartController** i wzbogacona ona jest wartością **WHSWorkExecuteMode** z opcji **StartProdOrder**. Używane są te same wystąpienia oparte na **SysExtension**, które były używane w klasach **WHSWorkExecuteDisplay**, co pomaga utworzyć wystąpienia kontrolera, gdy użytkownik wykonuje dla tego trybu element menu.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
public class ProdProcessGuideProductionStartController extends ProcessGuideController
```

> [!NOTE]
> Wzorcem nazewnictwa klasy jest **\<FunctionalArea\>ProcessGuide\<Businessprocessname\>Controller**. Jest to wzorzec używany w klasach kontrolera i rozszerzany na inne klasy.


## <a name="building-the-first-step"></a>Tworzenie pierwszego kroku

Następnie, aby zdefiniować pierwszy krok, utwórz klasę **ProdProcessGuidePromptProductionIdStep**, rozszerzając z **ProcessGuideStep**.

Zadanie tworzenia wystąpienia klasy jest delegowane do fabryki kroków, która jest wywoływana przez klasę podstawową **ProcessGuideController**. Domyślna implementacja fabryki tworzy wystąpienie kroku na podstawie nazwy. Dlatego aby utworzyć wystąpienia **ProdProcessGuidePromptProductionIdStep** jako pierwszego kroku w kontrolerze, należy wykonać dwie czynności:

-   Rozszerzanie klasy **ProdProcessGuidePromptProductionIdStep** za pomocą atrybutu **ProcessGuideStepName**.

    ```xpp
    [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))] public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
    ```

-   W klasie kontrolera zaimplementuj metodę abstrakcyjną **initialStepName()**, aby zwrócić nazwę kroku.

    ```xpp
    protected final ProcessGuideStepName initialStepName()
    {
        return classStr(ProdProcessGuidePromptProductionIdStep);
    }
    ````   
    
> [!NOTE]
> Wartość w atrybucie **ProcessGuideStepName** nie musi dokładnie odpowiadać nazwie klasy, tak jak pokazano powyżej. Jednak zastosowanie tych zasad zapewnia jednolitość i ogólne bezpieczeństwo typów wszystkich odwołań podczas używania klasy. Zalecane jest używanie tej konwencji nazewnictwa.
>
> Tworzenie wystąpienia kroku opartego na **ProcessGuideStepName** jest implementowanie w klasie **ProcessGuideStepDefaultFactory**. W rzadkim przypadku, gdy na potrzeby tworzenia wystąpienia kroku chcesz użyć innej strategii, należy wykonać następujące czynności:
> -   Utwórz nową klasę fabryki odziedziczoną po **ProcessGuidStepAbstractFactory**.
> -   Opcjonalnie można utworzyć nową klasę parametrów implementując interfejs **ProcessGuideIStepCreationParameters** zawierający parametry potrzebne fabryce.
> -   W klasie kontrolera zastąp metody **stepFactory()** i **stepCreationParameters()**, aby zwrócić powyższą fabrykę i parametry.

Następny krok to implementowanie funkcji klasy **ProdProcessGuidePromptProductionIdStep**. Należy zaimplementować logikę tworzenia interfejsu użytkownika, przetwarzania danych wprowadzonych przez użytkownika i określania, kiedy krok zostanie ukończony.

### <a name="building-the-user-interface-for-the-first-step"></a>Tworzenie interfejsu użytkownika dla pierwszego kroku

Interfejs użytkownika jest budowany przy użyciu klasy dziedziczonej po klasie abstrakcyjnej **ProcessGuidePageBuilder**. W tym kroku nadaj klasie nazwę reprezentującą jej działanie — **ProdProcessGuidePromptProductionIdPageBuilder**.

Mechanizm tworzenia wystąpienia klasy jest podobny do tworzenia wystąpienia kroku z kontrolera. 

-   Rozszerzanie klasy **ProdProcessGuidePromptProductionIdPageBuilder** za pomocą atrybutu **ProcessGuidePageBuilderName**.

    ```xpp
    [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))] public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
    ```

-   W klasie **ProdProcessGuidePromptProductionIdStep** zaimplementuj abstrakcyjną metodę **pageBuilderName()** w celu zwrócenia tej nazwy.

    ```xpp
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
    }
    ```    

> [!TIP]
> Podobnie jak w przypadku fabryki kroków, dla fabryki konstruktora strony istnieje także zaimplementowany wzorzec fabryki abstraktu. Więc w rzadkim przypadku, gdy na potrzeby tworzenia wystąpienia konstruktora strony chcesz użyć innej strategii, możesz wykonać następujące czynności:
> - Utwórz nową klasę fabryki odziedziczoną po **ProcessGuidePageBuilderAbstractFactory**.
> - Opcjonalnie można utworzyć nową klasę parametrów implementując interfejs **ProcessGuideIPageBuilderCreationParameters** zawierający parametry potrzebne fabryce.
> - W klasie kroku zastąp metody **pageBuilderFactory()** i **pageBuilderCreationParameters()**, aby zwrócić powyższą fabrykę i parametry.

Do zaimplementowania interfejsu użytkownika jest potrzebna strona z jednym polem tekstowym, aby wprowadzić identyfikator zlecenia produkcyjnego oraz przyciski **OK** i **Anuluj**. Przycisk **Anuluj** powinien wyjść z procesu.

Aby to zaimplementować, należy zastąpić dwie metody w klasie **ProdProcessGuidePromptProductionIdPageBuilder**:

-   Użyj metody **addDataControls()** w celu dodania pola tekstowego.

    ```xpp
    protected final void addDataControls(ProcessGuidePage _page)
    {
        _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
    }
    ```   

-   Użyj metody **addActionControls()** w celu dodania przycisków **OK** i **Anuluj**.

    ```xpp
    protected final void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelExitProcess));
    }
    ``` 

Powoduje to dodanie formantów danych i przycisków. Jeśli jednak chcesz utworzyć ekran za pomocą przeplatanych formantów danych i przycisków, możesz zastąpić metodę **addControls()** w celu zapewnienia elastycznego działania.

Dodatkowy scenariusz do rozważenia to sposób przebudowy strony w razie niepowodzenia weryfikacji, na przykład w przypadku, gdy użytkownik wprowadzi błędny identyfikator zlecenia produkcyjnego. Klasa bazowa **ProcessGuidePageBuilder** implementuje zachowanie domyślne, które odbudowuje interfejs użytkownika, czyści zeskanowaną wartość i dodaje formant błędu z komunikatem o błędzie. Nie trzeba dodawać kodów do obsługi błędów, ponieważ jest to zachowanie domyślne.

> [!TIP]
> Aby zaimplementować niestandardowe zachowanie interfejsu użytkownika w przypadku wystąpienia błędów, można zastąpić jedną lub więcej metod **rebuildFromRequestPage()**, **isErrorState()** i **reuseRequestPageOnError()**.

### <a name="processing-the-user-entered-data-in-the-first-step"></a>Przetwarzanie danych wprowadzonych przez użytkownika w pierwszym kroku

Przetwarzanie danych odbywa się w klasie **ProcessGuideDataProcessorDefault**, która z kolei wywołuje starszą klasę **WhsRfControlData**. To działanie domyślne nie wymaga żadnych zmian, a **WhsRfControlData** już zawiera logikę sprawdzania poprawności pola **ProdId**, więc nie trzeba zapisywać żadnej logiki do jego obsługi. W przypadku wymaganych rozszerzeń logiki weryfikacji należy wziąć pod uwagę użycie mechanizmu rozszerzenia opartego na **WhsControl**.

### <a name="determine-if-the-first-step-is-complete"></a>Określ, czy pierwszy krok został ukończony

Gdy sprawdzanie poprawności się powiedzie, czas oznaczyć krok jako zakończony. Można to zrobić w klasie podstawowej, ale trzeba zaimplementować warunek, aby określić zakończenie etapu. Robi to poniższa metoda zastąpienia.

```xpp
protected final boolean isComplete()
{
    WhsrfPassthrough pass = controller.parmSessionState().parmPass();
    ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);
        return (prodId != '');
}
```   

### <a name="step-two-view-order-details-and-confirm"></a>Krok 2: wyświetl szczegóły zamówienia i potwierdź

W drugim kroku procesu użytkownikowi wyświetlany jest ekran ze szczegółami dotyczącymi zamówienia. Użytkownik może kliknąć przycisk **OK**, aby potwierdzić rozpoczęcie zlecenia produkcyjnego, lub przycisk **Anuluj**, aby wrócić do rozpoczęcia procesu. W tym przykładzie nadaj krokowi nazwę **ProdProcessGuideConfirmProductionOrderStep** i klasie konstruktora stron **ProdProcessGuideConfirmProductionOrderPageBuilder**.

Klasa ProdProcessGuideConfirmProductionOrderStep wygląda jak ukazano poniżej.

```xpp
[ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
{
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
     }
}
```     

Ponieważ w tym miejscu użytkownik nie wprowadza żadnych wartości, nie ma potrzeby zastępowania metody **isComplete()**. Krok jest ukończony, gdy użytkownik kliknie przycisk **OK**.

Klasa konstruktora stron zastępuje metodę **addDataControls()**, aby dodać trzy etykiety. Pierwsza etykieta zawiera identyfikator zlecenia produkcyjnego, druga zawiera informacje o pozycji (takie jak identyfikator pozycji, wymiary lub opis), a trzecia zawiera ilość i jednostkę miary.

Następnie opcja **addActionControls()** zostanie zastąpiona, aby dodać 2 przyciski — przycisk **OK** oraz przycisk **Anuluj**, aby anulować proces i wrócić do jego początku.

```xpp
/// <summary>
/// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
/// and then confirm.
/// </summary>
[ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
{
    protected void addDataControls(ProcessGuidePage _page)
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;
        
        _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
        _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
        _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

        if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
        {
            _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
        }
    }

    protected void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelResetProcess));
    }
```

> [!NOTE]
> Ten sam kod źródłowy dla metod X++ można znaleźć w tym temacie, korzystając z Explorera aplikacji. Przefiltruj według nazwy klasy, a następnie kliknij prawym przyciskiem myszy nazwę klasy i wybierz polecenie **Wyświetl kod**.

### <a name="step-3-start-the-production-order"></a>Krok 3: rozpoczynanie zlecenia produkcyjnego

Na trzecim etapie jest wykonywana logika biznesowa rozpoczęcia zlecenia produkcyjnego. Ten krok różni się nieco od poprzednich kroków, w tym przypadku nie ma interfejsu użytkownika. Ten krok jest wykonywany w trybie dyskretnym, gdy użytkownik kliknie przycisk **OK** w poprzednim kroku.

Klasa abstrakcyjna **ProcessGuideStepWithoutPrompt** implementuje domyślne zachowanie dla takich kroków. Z tego powodu bieżący krok powinien rozszerzyć klasę **ProcessGuideStepWithoutPrompt** i zastąpić metodę **doExecute()**.

W poniższym przykładzie pokazano implementację klasy i metody **doExecute()**. Metoda po prostu pobiera identyfikator zamówienia i identyfikator użytkownika ze stanu sesji i wywołuje metodę uruchomienia tego zlecenia produkcyjnego.

```xpp
/// <summary>
/// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
/// </summary>
[ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
{
    protected final void doExecute()
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        WhsWorkExecute workExecute = WhsWorkExecute::construct();
        workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

        this.addProcessCompletionMessage();

        super();
    }

}
```

W przypadku wyjątku logika obsługi wyjątków struktury zapewnia, że proces będzie wycofany do poprzedniego kroku.

> [!NOTE]
> Wywołanie metody **addProcessCompletionMessage()** powoduje dodanie komunikatu „Praca zakończona” do parametrów nawigacji. Następny krok (przy założeniu, że ma interfejs użytkownika) spowoduje wyświetlenie tego komunikatu. Klasy podstawowe obsługują tę logikę i w celu osiągnięcia tego działania nie trzeba dodawać określonego kodu do klas procesów.


### <a name="building-the-navigation-through-the-steps"></a>Tworzenie nawigacji przez kroki

Klasa bazowa **ProcessGuideController** inicjuje klasę **ProcessGuideNavigationAgentDefault**, która bazuje na wstępnie zdefiniowanej marszrucie nawigacji, będącej prostą mapą kroków źródłowych i docelowych. W przypadku scenariusza rozpoczęcia produkcji ta implementacja wystarcza, ponieważ nie ma rozgałęzienia warunkowego. W związku z tym, aby zdefiniować marszrutę nawigacji, należy zastąpić tylko metodę **initializeNavigationRoute()**.

```xpp
    protected ProcessGuideNavigationRoute initializeNavigationRoute()
    {
        ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
        navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

        return navigationRoute;
    }
```

Istnieją procesy, które będą zawierać rozgałęzienia warunkowe (oparte na akcjach użytkownika lub dowolnych innych warunkach). W przypadku takich procesów należy wykonać następujące czynności:

-   Zastosuj określone agenty nawigacji odziedziczone po klasie **ProcessGuideNavigationAgent**.

-   Implementowanie określonej fabryki agentów nawigacji dziedziczonej po klasie **ProcessGuideNavigationAgentAbstractFactory**, zawierającej logikę tworzenia wystąpienia prawidłowego agenta nawigacji na podstawie bieżącego kroku, stanu sesji, akcji użytkownika lub innej logiki.

-   Opcjonalnie zastąpienie **navigationAgentCreationParameters()** w klasie kontrolera w celu przekazania odpowiednich parametrów.

-   Zastąp **navigationAgentFactory()** w kontrolerze, aby utworzyć wystąpienie fabryki agenta nawigacji utworzonej powyżej.

### <a name="action-classes"></a>Klasy akcji

Klasy akcji reprezentują akcje użytkownika, więc w tym przykładzie użyto akcji **OK** w celu pokazania sposobu ich tworzenia.

```xpp
[ProcessGuideActionName(#ActionOK)]
public class ProcessGuideOKAction extends ProcessGuideAction
{
    public final str label()
    {
        return "@SYS5473";
     }
     protected final void doExecute()
     {
        step.executeOKAction();
      }
}
```    

Klasa musi implementować 2 metody abstrakcyjne:

-   **label()** zwraca etykietę, która ma być wyświetlana w kontrolce przycisku powiązanej z tą akcją.

-   **doExecute()**, która wykonuje akcję. Jak już wymieniono wcześniej, przycisk **OK** po prostu wykonuje wywołanie zwrotne do kroku. Jednak inne akcje mogą mieć bardziej złożoną logikę.

Tworzenie wystąpienia akcji za pomocą struktury **SysExtension** na podstawie atrybutu **ProcessGuideActionName**. Podobnie jak w przypadku tworzenia wystąpienia konstruktorów stron, klasa kroku implementuje domyślną fabryki akcji i można ją zastąpić. Konstruktor stron dodaje formant przycisku w ten sposób.

```xpp
_page.addButton(step.createAction(#ActionOK), true);
```

W ten sposób pyta krok o utworzenie klasy akcji dla przekazanej nazwy i wiąże tę akcję z przyciskiem.

### <a name="summary"></a>Sumarycznie

Aby podsumować wszystko, co zostało objaśnione w tym temacie, oto pełne podsumowanie kodu potrzebnego w tym procesie:

1.  **ProdProcessGuideProductionStartController**

    1.  Zastąp **initialStepName()**, aby podać nazwę pierwszego kroku.
    2.  Zastąp **initializeNavigationRoute()**, aby skonstruować mapę nawigacji.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideProductionStartController</c> class is the controller class for the production order start process guide.
        /// </summary>
        [WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
        public class ProdProcessGuideProductionStartController extends ProcessGuideController
        {
            protected ProcessGuideStepName initialStepName()
            {
                return classStr(ProdProcessGuidePromptProductionIdStep);
            }

            protected ProcessGuideNavigationRoute initializeNavigationRoute()
            {
                ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
                navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

                return navigationRoute;
            }

        }
        ```

2.  **ProdProcessGuidePromptProductionIdStep**

    1.  Zastąp **isComplete()**, aby określić, kiedy krok jest traktowany jako ukończony.
    2.  Zastąp **pageBuilderName()** w celu określenia konstruktora stron, który ma być używany.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdStep</c> represents a step that 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))]
        public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
        {
            protected boolean isComplete()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);

                return (prodId != '');
            }

            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuidePromptProductionIdPageBuilder**

    1.  Zastąp **addDataControls()**, aby dodać pole tekstowe **Identyfikator produkcji**.
    2.  Zastąp **addActionControls()** w celu dodania przycisków **OK** i **Anuluj**.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdPageBuilder</c> class builds a page 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))]
        public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelExitProcess));
            }

        }
        ```

4.  **ProdProcessGuideConfirmProductionOrderStep**

    1.  Zastąp **pageBuilderName()** w celu określenia konstruktora stron, który ma być używany.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderStep</c> class represents the step for viewing production order
        /// details and confirming the same.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
        public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
        {    
            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuideConfirmProductionOrderPageBuilder**

    1.  Zastąp **addDataControls()**, aby dodać etykiety z informacjami o zamówieniu, pozycji i ilości.

    2.  Zastąp **addActionControls()** w celu dodania przycisków **OK** i **Anuluj**.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
        /// and then confirm.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
        public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;

                _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
                _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
                _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

                if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
                {
                    _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
                }
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelResetProcess));
            }

        ```

        > [!NOTE]
        > Metoda **generateItemInfoForProdId()** używana do generowania etykiet informacji o pozycji jest wykluczona z tego tematu. Ta metoda wysyła zapytanie do kilku tabel w celu uzyskania identyfikatora pozycji, opisu i wymiarów. Jeśli chcesz lepiej zrozumieć **generateItemInfoForProdId()**, sprawdź kod źródłowy.

4.  **ProdProcessGuideStartProductionOrderStep**

    1.  Aby wykonać proces rozpoczęcia produkcji, należy zastąpić metodę **doExecute()** i dodać komunikat o zakończeniu procesu.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
        public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
        {
            protected final void doExecute()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                WhsWorkExecute workExecute = WhsWorkExecute::construct();
                workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

                this.addProcessCompletionMessage();

                super();
            }

        }
        ```

> [!NOTE]
> Zauważ, że wiele typowych wzorców (regenerowanie interfejsu użytkownika w przypadku błędu, ustawianie komunikatu o zakończeniu procesu, zachowania **OK** i **Anuluj**) zostało przeniesionych do struktury — w związku deweloper aplikacji nie musi tracić czasu na pisanie gotowego kodu, który nie tylko może zawierać błędy, lecz także istnieje ryzyko niespójnego zachowania między procesami. Jeśli jednak scenariusz wymaga odchylenia od wspólnej ścieżki, deweloperowi aplikacji przedstawiana jest opcja nadpisania odpowiednich metod — ale jest to zamierzone odchylenie, które jest jawne i możliwe do śledzenia.


### <a name="extending-a-business-process"></a>Rozszerzanie procesu biznesowego

Do tej pory w tym temacie opisano sposób tworzenia nowego procesu przy użyciu struktury **ProcessGuide**. W tej ostatniej sekcji znajduje się kilka przykładów możliwości przedłużenia tego procesu biznesowego.

### <a name="add-a-step-in-a-flow-using-processguidenavigationagentdefault"></a>Dodawanie kroku w przepływie (przy użyciu ProcessGuideNavigationAgentDefault)

Miejsce rozszerzania:

-   Element podrzędny klasy **ProcessGuideController** dla procesu.

Sposób rozszerzania:

-   Rozszerz metodę **initializeNavigationRoute()** w klasie kontrolera i wywołaj metodę **addFollowingStep()** w klasie **ProcessGuideNavigationRoute**.

### <a name="add-a-step-in-a-flow-using-custom-navigation-agent"></a>Dodawanie kroku w przepływie (przy użyciu niestandardowego agenta nawigacji)

Miejsce rozszerzania:

-   Element podrzędny agenta **ProdProcessGuideNavigationAgentFactory/ProdProcessGuideNavigationAgent**.

Sposób rozszerzania:

-   Utwórz nową klasę podrzędną **ProcessGuideNavigationAgent**, która zwraca żądaną nazwę kroku.

-   Utwórz nową klasę pochodzącą z **ProcessGuideNavigationAgentFactory**, która warunkowo zwraca utworzonego powyżej agenta nawigacji.

-   Rozszerz metodę **navigationAgentFactory()** w klasie kontrolera, aby zwrócić utworzoną powyżej fabrykę.

### <a name="add-a-new-control-in-the-ui-of-an-existing-step"></a>Dodaj nowy formant w interfejsie użytkownika istniejącego kroku 

Miejsce rozszerzania:

-   Element podrzędny konstruktora **ProdProcessGuidePageBuilder** dla kroku.

Sposób rozszerzania:

-   Rozszerz metodę **addDataControls()** i dodaj dodatkowy formant.

### <a name="complete-overhaul-of-the-user-interface-in-an-existing-step"></a>Kompletny przegląd interfejsu użytkownika w istniejącym kroku

Miejsce rozszerzania:

-   Element podrzędny kroku **ProdProcessGuideStep**.

Sposób rozszerzania:

-   Utwórz nową klasę podrzędną klasy **ProdProcessGuidePageBuilder** i zaimplementuj żądany interfejs użytkownika.

-   Rozszerz metodę **pageBuildeName()** w klasie kroku, aby zwrócić **ProcessGuidePageBuilderNameAttribute** dla klasy utworzonej powyżej.

### <a name="alter-logic-when-a-step-is-considered-complete"></a>Zmień logikę, gdy krok jest traktowany jako zakończony

Miejsce rozszerzania:

-   Element podrzędny kroku **ProdProcessGuideStep**.

Sposób rozszerzania:

-   Rozszerz metodę **isComplete()** w celu utworzenia dodatkowej logiki.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]