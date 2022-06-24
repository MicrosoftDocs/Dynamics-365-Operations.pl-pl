---
title: Ustawianie prognozowania popytu
description: W tym artykule opisano ustawienia zadania, które należy wykonać, by przygotować się do prognozowania popytu.
author: t-benebo
ms.date: 11/23/2021
ms.topic: article
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10a211e0e20f22dfbfdb4923841808750b6ed71b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901010"
---
# <a name="demand-forecasting-setup"></a>Ustawianie prognozowania popytu

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób konfigurowania prognozowania popytu.  

## <a name="item-allocation-keys"></a>Klucze alokacji produktów

Klucze alokacji produktów ustalają grupy pozycji. Prognoza popytu jest obliczana dla towaru i jego wymiarów tylko wtedy, gdy towar jest częścią klucza alokacji towaru. Ta reguła zostaje wymuszona w celu pogrupowania dużej liczby towarów, tak aby można było szybciej utworzyć prognozy popytu. Prognozy są tworzone tylko na podstawie danych historycznych.

Towar i jego wymiary muszą być częścią tylko jednego klucza alokacji produktów, o ile klucz jest używany podczas tworzenia prognozy.

Aby utworzyć klucze alokacji pozycji i dodać do nich jednostkę magazynowania (SKU), należy wykonać następujące kroki.

1. Przejdź do **Planowanie główne \> Konfiguracja \> Prognozowanie popytu \> Klucze alokacji pozycji**.
1. Wybierz istniejący klucz alokacji pozycji w okienku listy lub wybierz **Nowy** w okienku akcji, aby utworzyć nowy. W nagłówku nowego lub wybranego klucza ustaw następujące pola:

    - **Klucz alokacji pozycji** — wprowadź unikatową nazwę klucza.
    - **Nazwa** — umożliwia wprowadzenie opisowej nazwy klucza.

1. Aby dodać pozycje do wybranego klucza alokacji pozycji lub usunąć pozycje, należy wykonać jedną z poniższych czynności:

    - Na skróconej karcie **Alokacja pozycji** użyj przycisków **Nowy** i **Usuń** na pasku narzędzi, aby dodać lub usunąć pozycje w razie potrzeby. Dla każdego wiersza wybierz numer pozycji, a następnie w pozostałych kolumnach przypisz wymagane wartości wymiarów. Wybierz opcję **Wyświetl wymiary** na pasku narzędzi, aby zmienić zestaw kolumn wymiarów wyświetlanych na siatce. (Wartość w kolumnie **Procent** jest ignorowana podczas generowania prognoz popytu).
    - Aby dodać do klucza wiele pozycji, wybierz opcję **Przypisz pozycje** w okienku akcji, aby otworzyć stronę, na której można znaleźć wiele pozycji i przypisać je do wybranego klucza.

> [!IMPORTANT]
> Należy zachować ostrożność, aby w każdym kluczu alokacji pozycji uwzględnić tylko właściwe pozycje. Niepotrzebne pozycje mogą powodować zwiększenie kosztów, jeśli korzystasz z usługi uczenia maszynowego Microsoft Azure.

## <a name="intercompany-planning-groups"></a>Grupy planowania międzyfirmowego

Prognozowanie popytu może generować prognozy w obrębie firmy. W aplikacji Dynamics 365 Supply Chain Management firmy, które są planowane razem, są grupowane w tej samej grupie planowania międzyfirmowego. Aby określić dla poszczególnych firm, które klucze alokacji pozycji powinny być uwzględniane w prognozowaniu popytu, należy skojarzyć klucz alokacji pozycji z elementem członkowskim grupy planowania międzyfirmowego.

> [!IMPORTANT]
> Optymalizacja planowania nie obsługuje obecnie grup planowania międzyfirmowego. Aby przeprowadzić planowanie międzyfirmowe, które korzysta z optymalizacji planowania, należy skonfigurować zadania wsadowe planowania głównego, które zawierają plany główne dla wszystkich odpowiednich firm.

Aby skonfigurować grupy planowania międzyfirmowego, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Planowanie główne \> Ustawienia \> Grupy planowania międzyfirmowego**.
1. Wybierz istniejącą grupę planowania w okienku listy lub wybierz **Nowy** w okienku akcji, aby utworzyć nową. W nagłówku nowej lub wybranej grupy ustaw następujące pola:

    - **Nazwa** — wprowadź unikatową nazwę grupy planowania.
    - **Opis** — wprowadź krótki opis grupy planowania.

1. Na skróconej karcie **Członkowie grupy planowania międzyfirmowego** użyj przycisków na pasku narzędzi, aby dodać wiersz dla każdej firmy (osoby prawnej), która ma być częścią grupy. Dla każdego wiersza ustaw następujące pola:

    - **Firma** — wybierz nazwę firmy (osoby prawnej), która jest członkiem wybranej grupy.
    - **Sekwencja planowania** — przypisz zamówienie, w odniesieniu do którego firma powinna być przetwarzana w stosunku do innych firm. Najpierw są przetwarzane niskie wartości. To zamówienie może być ważne, jeśli popyt jednej firmy wpływa na inne firmy. W tych przypadkach firma, która dostarcza popyt, powinna być przetworzona jako ostatnia.
    - **Plan główny** — wybierz plan główny do wyzwolenia w bieżącej firmie.
    - **Automatyczne kopiowanie do planu statycznego** — zaznacz to pole wyboru, aby skopiować wynik planu do planu statycznego.
    - **Automatyczne kopiowanie do planu dynamicznego** — zaznacz to pole wyboru, aby skopiować wynik planu do planu dynamicznego.

1. Domyślnie, jeśli do członków grupy planowania firmowego nie są przypisane klucze alokacji produktów, prognoza popytu jest obliczana dla wszystkich pozycji przypisanych do wszystkich kluczy alokacji z wszystkich firm. Dodatkowe opcje filtrowania dla firm i kluczy alokacji pozycji są dostępne w oknie dialogowym **Generowanie bazowej prognozy statystycznej** (**Planowanie główne \> Prognozowanie \> Prognozowanie popytu \> Generowanie bazowej prognozy statystycznej**). Aby przypisać klucze alokacji pozycji do firmy w wybranej grupie planowania międzyfirmowego, wybierz firmę, a następnie na skróconej karcie **Członkowie grupy planowania międzyfirmowego** wybierz opcję **Klucze alokacji pozycji** na pasku narzędzi.

> [!IMPORTANT]
> Należy zachować ostrożność, aby w każdej grupie planowania międzyfirmowego uwzględnić tylko właściwe klucze alokacji pozycji. Niepotrzebne pozycje mogą powodować zwiększenie kosztów, jeśli korzystasz z usługi Azure Machine Learning.

## <a name="set-up-demand-forecasting-parameters"></a><a name="parameters"></a>Konfigurowanie parametrów prognozowania popytu

Strona **Parametry prognozowania popytu** umożliwia skonfigurowanie kilku opcji sterujących działaniem prognozowania popytu w Twoim systemie.

### <a name="open-the-demand-forecasting-parameters-page"></a>Otwieranie strony parametrów prognozowania popytu

Aby skonfigurować parametry prognozowania popytu, wybierz kolejno opcje **Planowanie główne \> Ustawienia \> Prognozowanie popytu \> Parametry prognozowania popytu**. Prognozowanie popytu jest uruchamiane w obrębie firmy, dlatego to ustawienie ma charakter globalny. Innymi słowy, ma zastosowanie do wszystkich osób prawnych (firm).

### <a name="general-settings"></a>Ustawienia ogólne

Użyj karty **Ogólne** na stronie **Parametry prognozowania popytu**, aby zdefiniować ogólne ustawienia prognozowania popytu.

#### <a name="demand-forecast-unit"></a>Jednostka prognozy popytu

Prognozowanie popytu generuje prognozy w ilościach. W związku z tym w polu **Jednostka prognozy popytu** należy określić jednostki miary, w których mają być wyrażone ilości. To pole definiuje jednostkę, która będzie używana we wszystkich prognozach popytu, niezależnie od zwykłych jednostek magazynowych dla każdego produktu. Użycie spójnej jednostki prognozy zapewnia, że agregacja i rozdział procentowy mają sens. Aby uzyskać więcej informacji o agregacji i rozdziale procentowym, zobacz [Ręczne korekty prognozy bazowej](manual-adjustments-baseline-forecast.md).

Dla każdej jednostki miary używanej dla jednostek SKU zawartych w prognozie popytu należy sprawdzić, czy istnieje reguła konwersji dla jednostki miary i ogólna jednostka miary prognozowania wybrana w tym miejscu. Podczas generowania prognozy rejestrowana jest lista pozycji, które nie mają konwersji jednostki miary. Dzięki temu konfigurację można łatwo poprawić. Aby uzyskać więcej informacji o jednostkach miary i sposobie ich konwertowania, zobacz [Zarządzanie jednostkami miary](../pim/tasks/manage-unit-measure.md).

#### <a name="transaction-types"></a>Typy transakcji

Pola na skróconej karcie **Typy transakcji** służą do wybierania typów transakcji stosowanych podczas generowania bazowej prognozy statystycznej.

Prognozowanie popytu może służyć do przewidywania popytu zależnego i popytu niezależnego. Jeśli na przykład tylko opcja **Zamówienie sprzedaży** jest ustawiona na *Tak* i wszystkie pozycje objęte prognozowaniem popytu to pozycje sprzedawane, platforma oblicza popyt niezależny. Można jednak dodawać składniki podrzędne o znaczeniu krytycznym do kluczy alokacji produktów i uwzględniać je w prognozie popytu. W takim przypadku, jeśli opcja **Linia produkcyjna** jest ustawiona na *Tak*, obliczana jest prognoza zależna.

Za pomocą karty **Klucze alokacji pozycji** można zastąpić typy transakcji dla co najmniej jednego klucza alokacji pozycji. Ta karta zawiera podobne pola.

#### <a name="choose-how-to-create-the-baseline-forecast"></a>Wybieranie sposobu tworzenia prognozy bazowej

Pole **Strategia generowania prognozy** umożliwia wybór metody używanej do tworzenia prognozy bazowej. Dostępne są trzy metody:

- *Kopiuj na popycie historycznym* — tworzenie prognoz tylko przez kopiowanie danych historycznych.
- *Azure Machine Learning Service* — użyj modelu prognozy, który używa usługi Azure Machine Learning Service. Usługa Azure Machine Learning Service to bieżące rozwiązanie do uczenia maszynowego dla platformy Azure. Z tego względu zaleca się używanie jej w przypadku korzystania z modelu prognozy.
- *Azure Machine Learning* — użyj modelu prognozy, który używa usługi programu Azure Machine Learning Studio (wersja klasyczna). Program Azure Machine Learning Studio (wersja klasyczna) jest przestarzały i wkrótce zostanie usunięte z platformy Azure. Dlatego zalecamy wybranie usługi *Azure Machine Learning Service*, jeśli konfigurujesz prognozowanie popytu po raz pierwszy. Jeśli obecnie używasz programu Azure Machine Learning Studio (wersja klasyczna), jak najszybciej zaplanuj przełączenie do usługi Azure Machine Learning Service.

Za pomocą karty **Klucze alokacji pozycji** można zastąpić metodę generowania prognozy dla co najmniej jednego klucza alokacji pozycji. Ta karta zawiera podobne pola.

#### <a name="override-default-forecast-algorithm-parameters-globally"></a>Globalne zastępowanie domyślnych parametrów algorytmu prognozy

Domyślne parametry i wartości algorytmu prognozy są przypisywane na stronie **Parametry prognozowania popytu** (**Parametry \> Ustawienia \> Prognozowanie popytu \> Parametry prognozowania popytu**). Można je jednak zastąpić globalnie, używając skróconej karty **Parametry algorytmu prognozy** na karcie **Ogólne** na stronie **Parametry prognozowania popytu**. (Można je również zastąpić dla określonych kluczy alokacji, korzystając z karty **Klucze alokacji pozycji** na stronie **Parametry prognozowania popytu**).

Użyj przycisków **Dodaj** i **Usuń** na pasku narzędzi, aby określić wymaganą kolekcję zastąpień parametrów. Dla każdego parametru z listy wybierz wartość w polu **Nazwa**, a następnie wprowadź odpowiednią wartość w polu **Wartość**. Wszystkie parametry, które nie są wymienione w tym miejscu, będą pobierać wartości z ustawień na stronie **Parametry prognozowania popytu**. Aby uzyskać więcej informacji na temat używania standardowego zestawu parametrów i wybierania ich wartości, zobacz sekcję [Domyślne parametry i wartości modeli prognozowania popytu](#model-parameters).

### <a name="set-forecast-dimensions"></a>Ustawianie wymiarów prognozy

Wymiar prognozy wskazuje poziom szczegółów, które dla którego prognoza jest definiowana. Firma, witryna i klucz alokacji pozycji to wymagane wymiary prognozy. Można również tworzyć prognozy na poziomie magazynu, stanu zapasów, grupy klientów, konta klienta, kraju/regionu, stanu i/lub poziomu pozycji oraz na wszystkich poziomach wymiarów pozycji. Użyj karty **Wymiary prognozy** na stronie **Parametry prognozowania popytu**, aby wybrać zestaw wymiarów prognozy, które są używane przy generowaniu prognozy popytu.

W dowolnym momencie można dodawać wymiary prognozy do listy wymiarów używanych do prognozowania popytu. Można też usunąć z listy wymiary prognozy. Ręczne korekty zostaną jednak utracone po dodaniu lub usunięciu wymiaru prognozy.

### <a name="set-up-overrides-for-specific-item-allocation-keys"></a>Ustawianie zastąpień dla określonych kluczy alokacji pozycji

Nie wszystkie pozycje działają w taki sam sposób z perspektywy prognozowania popytu. W związku z tym można określić zastąpienia specyficzne dla klucza alokacji dla większości ustawień zdefiniowanych na karcie **Ogólne**. Wyjątkiem jest jednostka prognozy popytu. Aby skonfigurować zastąpienia dla określonego klucza alokacji produktów, należy wykonać następujące kroki.

1. Na stronie **Parametry prognozowania popytu**, na karcie **Klucze alokacji pozycji** za pomocą przycisków paska narzędzi dodaj do siatki po lewej stronie klucze alokacji pozycji lub usuń je w zależności od potrzeb. Następnie wybierz klucz alokacji, dla którego chcesz skonfigurować zastąpienia.
1. Na skróconej karcie **Typy transakcji** włącz typy transakcji, które mają służyć do generowania bazowej prognozy statystycznej dla produktów należących do wybranego klucza alokacji. Ustawienia działają w ten sam sposób, jak na karcie **Ogólne**, ale dotyczą tylko wybranego klucza alokacji pozycji. Wszystkie ustawienia w tym miejscu (wartości *Tak* i *Nie*) zastępują wszystkie ustawienia **typów transakcji** na karcie **Ogólne**.
1. Na skróconej karcie **Parametry algorytmu prognozy** wybierz strategię generowania prognozy oraz zastąpienia parametrów algorytmu prognozy dla produktów należących do wybranego klucza alokacji. Ustawienia te działają w ten sam sposób, jak na karcie **Ogólne**, ale dotyczą tylko wybranego klucza alokacji pozycji. Użyj przycisków **Dodaj** i **Usuń** na pasku narzędzi, aby zdefiniować wymaganą kolekcję zastąpień parametrów. Dla każdego parametru z listy wybierz wartość w polu **Nazwa**, a następnie wprowadź odpowiednią wartość w polu **Wartość**. Aby uzyskać więcej informacji na temat używania standardowego zestawu parametrów i wybierania ich wartości, zobacz sekcję [Domyślne parametry i wartości modeli prognozowania popytu](#model-parameters).

### <a name="set-up-the-connection-to-the-azure-machine-learning-service"></a>Konfigurowanie połączenia z usługą Azure Machine Learning Service

Użyj karty **Azure Machine Learning Service**, aby skonfigurować połączenie z usługą Azure Machine Learning Service. To rozwiązanie jest jedną z opcji tworzenia prognozy bazowej. Te ustawienia na tej karcie mają wpływ tylko wtedy, gdy w polu **Strategia generowania prognozy** jest ustawiona usługa *Azure Machine Learning Service*.

Aby uzyskać więcej informacji dotyczących sposobu konfigurowania usługi Azure Machine Learning Service, a następnie używania ustawień w tym miejscu do nawiązywania połączenia z tą usługą, zobacz sekcję [Konfigurowanie usługi Azure Machine Learning Service](#setup-amls).

### <a name="set-up-the-connection-to-azure-machine-learning-studio-classic"></a>Konfigurowanie połączenia z programem Azure Machine Learning Studio (wersja klasyczna)

> [!IMPORTANT]
> Program Azure Machine Learning Service (wersja klasyczna) jest przestarzały. W związku z tym nie możesz już tworzyć jego nowych obszarów roboczych na platformie Azure. Program ten został zastąpiony przez usługę Azure Machine Learning Service, która zapewnia podobne funkcje i nie tylko. Jeśli jeszcze nie używasz usługi Azure Machine Learning, możesz rozpocząć korzystanie z usługi Azure Machine Learning Service. Jeśli masz już obszar roboczy utworzony dla programu Azure Machine Learning Studio (wersja klasyczna), możesz nadal używać go, dopóki ta funkcja nie zostanie całkowicie usunięta z platformy Azure. Zalecamy jednak jak najszybszą aktualizację do usługi Azure Machine Learning Service. Chociaż aplikacja będzie nadal ostrzegać o tym, że program Azure Machine Learning Studio (wersja klasyczna) jest przestarzały, nie będzie to mieć wpływu na wynik prognozowania. Aby uzyskać więcej informacji dotyczących nowej usługi Azure Machine Learning Service i sposobu jej konfigurowania, zobacz sekcję [Konfigurowanie usługi Azure Machine Learning Service](#setup-amls).
>
> W aplikacji Supply Chain Management można swobodnie przełączać się między nowymi i starymi rozwiązaniami do uczenia maszynowego, dopóki będzie dostępny stary obszar roboczy programu Azure Machine Learning Studio (wersja klasyczna).

Jeśli masz już dostępny obszar roboczy programu Azure Machine Learning Studio (wersja klasyczna), można go używać do generowania prognoz przez połączenie go z aplikacją Supply Chain Management. Możesz ustanowić to połączenie, używając karty **Azure Machine Learning** na stronie **Parametry prognozowania popytu**. (Ustawienia na tej karcie mają wpływ tylko wtedy, gdy w polu **Strategia generowania prognozy** jest ustawiona wartość *Azure Machine Learning*). Wprowadź następujące szczegóły dla swojego obszaru roboczego programu Azure Machine Learning Studio (wersja klasyczna):

- Klucz sieciowy API
- Końcowy URL usługi sieciowej
- Nazwa konta magazynu systemu Azure
- Klucz konta magazynu systemu Azure

> [!NOTE]
> Nazwa konta i klucz konta magazynu Azure systemu są wymagane tylko w przypadku używania niestandardowego konta magazynu. Jeśli została wdrożona wersja lokalna programu, musisz mieć niestandardowe konto magazynu na platformie Azure, aby usługa Machine Learning miała dostęp do danych historycznych.

## <a name="default-parameters-and-values-for-demand-forecasting-models"></a><a name="model-parameters"></a>Domyślne parametry i wartości modeli prognozowania popytu

Jeśli do generowania modeli planowania prognozy używane jest uczenie maszynowe, opcje uczenia maszynowego kontrolujesz, ustawiając wartości *parametrów algorytmu prognozowania*. Te wartości są wysyłane z aplikacji Supply Chain Management do usługi Azure Machine Learning. Strona **Parametry algorytmu prognozowania** steruje tym, jakie typy wartości należy określić i jakie wartości powinny być dostępne.

Aby skonfigurować domyślne parametry i wartości używane w modelu prognozowania popytu, wybierz kolejno opcje **Planowanie główne \> Ustawienia \> Prognozowanie popytu \> Parametry algorytmu prognozowania**. Zostanie określony standardowy zestaw parametrów. Każdy parametr ma następujące pola:

- **Nazwa** — nazwa parametru używana na platformie Azure. Zazwyczaj tej nazwy nie należy zmieniać, chyba że dostosowano eksperyment w usłudze Azure Machine Learning.
- **Opis** — nazwa pospolita parametru. Ta nazwa służy do identyfikowania parametru w innych miejscach systemu (na przykład na stronie **Parametry prognozowania popytu**).
- **Wartość** — domyślna wartość parametru. Wprowadzana wartość zależy od edytowanego parametru. 
- **Wyjaśnienie** — krótki opis parametru i sposobu jego używania. Ten opis zazwyczaj zawiera porady dotyczące prawidłowych wartości pola **Wartość**.

Domyślnie dostępne są następujące parametry. (Jeśli musisz przywrócić tę listę standardową, wybierz opcję **Przywróć** w okienku akcji).

- **Wartość procentowa poziomu ufności** — przedział wiarygodności zawiera zakres wartości będących dobrymi danymi szacunkowymi dla prognozy popytu. Wiarygodność na poziomie 95% oznacza, że występuje 5-procentowe ryzyko, że w przyszłości popyt wykroczy poza zakres wiarygodności.
- **Wymuszaj sezonowość** — określa, czy w modelu ma być używany określony typ sezonowości. Ten parametr dotyczy to tylko opcji ARIMA i ETS only. Opcje: *AUTOMATYCZNE (domyślne)*, *BRAK*, *DODATKOWE*, *ZWIELOKROTNIONE*.
- **Model prognozowania** — określa model prognozowania do użycia. Opcje: *ARIMA*, *ETS*, *STL*, *ETS+ARIMA*, *ETS+STL*, *WSZYSTKIE*. Aby wybrać model najlepszego dopasowania, użyj opcji *WSZYSTKIE*.
- **Maksymalna wartość prognozy** — określa maksymalną wartość, która ma być użyta dla prognoz. Format: + 1E[n] lub stała numeryczna.
- **Minimalna wartość prognozy** — określa minimalną wartość, która ma być użyta dla prognoz. Format: - 1E[n] lub stała numeryczna.
- **Brak podstawiania wartości** — określa sposób wypełniania przerw w danych historycznych. Opcje: *(wartość liczbowa)*, *ŚREDNIA*, *POPRZEDNIA*, *INTERPOLACJA LINIOWA*, *INTERPOLACJA WIELOMIANOWA*.
- **Brak zakresu podstawiania wartości** — określa, czy podstawianie wartości ma zastosowanie tylko do zakresu dat każdego z poszczególnych atrybutów stopnia szczegółowości, czy do całego zestawu danych. Dostępne są następujące opcje ustalania zakresu dat używanego przez system przy wypełnianiu luk w danych historycznych:

    - *GLOBAL* — system używa pełnego zakresu dat wszystkich atrybutów szczegółowości.
    - *HISTORY_DATE_RANGE* — system używa określonego zakresu dat zdefiniowanego przez pola **Od daty** i **Do daty** w grupie pól **Horyzont historyczny** w oknie dialogowym **Generowanie bazowej prognozy statystycznej**.
    - *GRANULARITY_ATTRIBUTE* — system używa zakresu dat aktualnie przetworzonego atrybutu szczegółowości.

    > [!NOTE]
    > Atrybut szczegółowości to kombinacja wymiarów prognozy, dla których wykonywana jest prognoza. Wymiary prognozy można zdefiniować na stronie **Parametry prognozowania popytu**.

- **Wskazówka sezonowości** — w przypadku danych sezonowych należy wprowadzić wskazówkę do modelu prognozowania w celu zwiększenia dokładności prognozy. Format: liczba całkowita, która reprezentuje liczbę przedziałów powtarzanego wzoru popytu. Na przykład wprowadź wartość *6* dla danych, które powtarzają się co sześć miesięcy.
- **Procent rozmiaru zestawu testowego** — procent danych historycznych przeznaczonych do użycia jako zestaw testowy w obliczeniach dokładności prognozy.

Wartości tych parametrów można zastąpić, przechodząc do obszaru **Planowanie główne \> Ustawienia \> Prognozowanie popytu \> Parametry prognozowania popytu**. Na stronie **Parametry prognozowania popytu** można zastąpić te parametry przy użyciu następujących sposobów:

- Użycie karty **Ogólne** do globalnego zastąpienia parametrów.
- Użycie karty **Klucze alokacji pozycji** do zastąpienia parametrów dla poszczególnych kluczy alokacji pozycji. Parametry, które są zastępowane dla określonego klucza alokacji pozycji mają wpływ tylko prognozę pozycji, które są skojarzone z tym kluczem alokacji pozycji.

> [!NOTE]
> Na stronie **Parametry algorytmu prognozowania** można używać przycisków w okienku akcji, dodawać parametry do listy lub usuwać parametry z listy. Zazwyczaj jednak nie należy korzystać z tego podejścia, chyba że dostosowano eksperyment w usłudze Azure Machine Learning.

## <a name="set-up-the-azure-machine-learning-service"></a><a name="setup-amls"></a>Konfigurowanie usługi Azure Machine Learning Service

Aplikacja Supply Chain Management oblicza prognozy popytu przy użyciu usługi Azure Machine Learning Service, którą musisz skonfigurować i uruchomić we własnej subskrypcji platformy Azure. W tej sekcji opisano sposób konfigurowania usługi Azure Machine Learning Service na platformie Azure, a następnie połączenia jej ze środowiskiem aplikacji Supply Chain Management.

### <a name="enable-the-azure-machine-learning-service-in-feature-management"></a>Włączanie usługi Azure Machine Learning Service w zarządzaniu funkcjami

Aby można było używać usługi Azure Machine Learning Service do prognozowania popytu, należy włączyć funkcję w aplikacji Supply Chain Management, aby umożliwić integrację. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Planowanie główne*
- **Nazwa funkcji:** *Azure Machine Learning Service na potrzeby prognozowania popytu*

### <a name="set-up-machine-learning-in-azure"></a><a name="ml-workspace"></a>Konfigurowanie uczenia maszynowego na platformie Azure

Aby umożliwić platformie Azure używanie uczenia maszynowego do przetwarzania prognoz, musisz skonfigurować w tym celu obszar roboczy usługi Azure Machine Learning. Masz do wyboru dwie opcje:

- Aby skonfigurować obszar roboczy, uruchamiając skrypt dostarczany przez Microsoft, postępuj zgodnie z instrukcjami w sekcji [Opcja 1. Uruchamianie skryptu w celu automatycznego konfigurowania sekcji obszaru roboczego usługi Machine Learning](#ml-workspace-script), a następnie przejdź do sekcji [Konfigurowanie parametrów połączenia z usługą Azure Machine Learning Service w aplikacji Supply Chain Management](#demand-forecast-parameters).
- Aby ręcznie skonfigurować obszar roboczy, postępuj zgodnie z instrukcjami w sekcji [Opcja 2. Ręczne konfigurowanie obszaru roboczego usługi Machine Learning](#ml-workspace-manual), a następnie przejdź do sekcji [Konfigurowanie parametrów połączenia z usługą Azure Machine Learning Service w aplikacji Supply Chain Management](#demand-forecast-parameters). Ta opcja zajmuje więcej czasu, ale zapewnia większą kontrolę.

#### <a name="option-1-run-a-script-to-automatically-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-script"></a>Opcja 1. Uruchamianie skryptu w celu automatycznego konfigurowania sekcji obszaru roboczego usługi Machine Learning

W tej sekcji opisano sposób skonfigurowania obszaru roboczego usługi Machine Larning przy użyciu zautomatyzowanego skryptu dostarczanego przez Microsoft. Jeśli wolisz, możesz ręcznie skonfigurować wszystkie zasoby, korzystając z instrukcji dostępnych w sekcji [Opcja 2. Ręczne konfigurowanie obszaru roboczego usługi Machine Learning](#ml-workspace-manual). Nie trzeba korzystać z obu opcji.

1. W witrynie GitHub otwórz [szablony prognozowania popytu aplikacji Dynamics 365 Supply Chain Management za pomocą repozytorium usługi Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) i pobierz następujące pliki:

    - quick_setup.ps1
    - sampleInput.csv
    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. Otwórz okno programu PowerShell i uruchom skrypt **quick_setup.ps1** pobrany w poprzednim kroku. Postępuj zgodnie z instrukcjami wyświetlanymi na ekranie. Skrypt skonfiguruje wymagany obszar roboczy, magazyn, domyślny magazyn danych i zasoby obliczeniowe. Mimo to wciąż należy utworzyć wymagane potoki, wykonując pozostałe kroki tej procedury. (Potoki stanowią sposób uruchamiania skryptów prognozowania z aplikacji Supply Chain Management).
1. W programie Azure Machine Learning Studio przekaż plik **sampleInput.csv** pobrany w kroku 1 do kontenera o nazwie *demplan-azureml*. (Skrypt quick_setup.ps1 utworzył ten kontener). Ten plik jest wymagany do opublikowania potoku i wygenerowania prognozy testowej. Aby uzyskać instrukcje, zobacz [Przekazywanie blokowego obiektu blob](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob).
1. W programie Azure Machine Learning Studio wybierz w nawigatorze pozycję **Notebooks**.
1. W strukturze **plików** znajdź następującą lokalizację: **\[Users/bieżący użytkownik\]/src**.
1. Przekaż pozostałe cztery pliki pobrane w kroku 1 do lokalizacji znalezionej w poprzednim kroku.
1. Wybierz właśnie przekazany plik **api_trigger.py** i uruchom go. Spowoduje to utworzenie potoku, który może być wyzwalany przez interfejs API.
1. Twój obszar roboczy został skonfigurowany. Przejdź do sekcji [Konfigurowanie parametrów połączenia usługi Azure Machine Learning Service w aplikacji Supply Chain Management](#demand-forecast-parameters).

#### <a name="option-2-manually-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-manual"></a>Opcja 2. Ręczne konfigurowanie obszaru roboczego usługi Machine Learning

W tej sekcji opisano sposób ręcznego konfigurowania obszaru roboczego usługi Machine Learning. Procedury opisane w tej sekcji należy wykonać tylko wtedy, gdy trzeba nie uruchamiać skryptu konfiguracji automatycznej, zgodnie z opisem w sekcji [Opcja 1. Uruchamianie skryptu w celu automatycznego konfigurowania sekcji obszaru roboczego usługi Machine Learning](#ml-workspace-script).

##### <a name="step-1-create-a-new-workspace"></a><a name="create-workspace"></a>Krok 1. Tworzenie nowego obszaru roboczego

Poniższa procedura służy do tworzenia nowego obszaru usługi Machine Learning.

1. Zaloguj się do witryny Azure Portal.
1. Otwórz usługę **Machine Learning**.
1. Wybierz pozycję **Utwórz** na pasku narzędzi, aby otworzyć kreatora **tworzenia**.
1. Wykonaj kolejne czynności w kreatorze, korzystając z instrukcje wyświetlanych na ekranie. Podczas pracy należy pamiętać o następujących kwestiach:

    - Użyj ustawień domyślnych, chyba że inne punkty na tej liście zalecają inne ustawienia.
    - Pamiętaj, aby wybrać region geograficzny, który pasuje do regionu, w którym jest wdrożona aplikacji Supply Chain Management. W przeciwnym razie niektóre dane mogą przejść przez granice regionów. Więcej informacji znajduje się w dalszej sekcji dotyczącej [klauzuli prywatności](#privacy) w tym artykule.
    - Użyj dedykowanych zasobów, takich jak grupy zasobów, konta magazynu, rejestry kontenerów, magazyny kluczy platformy Azure i zasobów sieciowych.
    - Na stronie **Ustawianie parametrów połączenia usługi Azure Machine Learning Service** w kreatorze musisz podać nazwę konta magazynu. Użyj konta dedykowanego do prognozowania popytu. Dane wejściowe i wyjściowe prognozowania popytu będą przechowywane na tym koncie magazynu.

Aby uzyskać więcej informacji, zobacz temat [Tworzenie obszaru roboczego](/azure/machine-learning/quickstart-create-resources#create-the-workspace).

##### <a name="step-2-configure-storage"></a><a name="config-storage"></a>Krok 2. Konfigurowanie magazynu

Użyj poniższej procedury, aby skonfigurować magazyn.

1. W witrynie GitHub otwórz [szablony prognozowania popytu aplikacji Dynamics 365 Supply Chain Management za pomocą repozytorium usługi Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) i pobierz plik **sampleInput.csv**.
1. Otwórz konto magazynu utworzone w sekcji [Krok 1. Tworzenie nowego obszaru roboczego](#create-workspace).
1. Postępuj zgodnie z instrukcjami w części [Tworzenie kontenera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container), aby utworzyć konteneter o nazwie *demplan-azureml*.
1. Przekaż plik **sampleInput.csv** pobrany w kroku 1 do utworzonego właśnie kontenera. Ten plik jest wymagany do opublikowania potoku i wygenerowania prognozy testowej. Aby uzyskać instrukcje, zobacz [Przekazywanie blokowego obiektu blob](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob).

##### <a name="step-3-configure-a-default-datastore"></a>Krok 3. Konfigurowanie domyślnego magazynu danych

Użyj poniższej procedury, aby skonfigurować domyślny magazyn danych.

1. W programie Azure Machine Learning Studio wybierz w nawigatorze pozycję **Magazyny danych**.
1. Utwórz nowy magazyn danych typu *Azure Blob Storage*, który wskazuje kontener usługi Blob Storage *demplan-azureml* utworzony w sekcji [Krok 2. Konfigurowanie magazynu](#config-storage). (Jeśli typem uwierzytelniania nowego magazynu danych jest *Klucz konta*, podaj klucz konta dla utworzonego konta magazynu. Aby uzyskać instrukcje, zobacz temat [Zarządzanie kluczami dostępu do konta magazynu](/azure/storage/common/storage-account-keys-manage?tabs=azure-portal)).
1. Ustaw nowy magazyn danych jako domyślny magazyn danych, otwierając jego szczegóły i wybierając pozycję **Ustaw jako domyślny magazyn danych**.

##### <a name="step-4-configure-compute-resources"></a><a name="config-compute-resources"></a>Krok 4. Konfigurowanie zasobów obliczeniowych

Aby uruchomić skrypty generowania prognoz, należy skorzystać z następującej procedury, aby skonfigurować zasób obliczeniowy w programie Azure Machine Learning Studio.

1. Otwórz stronę szczegółów obszaru roboczego usługi Machine Learning utworzonego w sekcji [Krok 1. Tworzenie nowego obszaru roboczego](#create-workspace). Znajdź wartość **internetowego adresu URL programu Studio** i wybierz link, aby go otworzyć.
1. W okienku nawigacji wybierz opcję **Obliczanie**.
1. Na karcie **Wystąpienia obliczeniowe** wybierz opcję **Nowe**, aby otworzyć kreatora, który pomoże Ci utworzyć nowe wystąpienie obliczeniowe. Postępuj zgodnie z instrukcjami wyświetlanymi na ekranie. Wystąpienie obliczeniowe będzie używane do tworzenia potoku prognozowania popytu (można je usunąć po opublikowaniu potoku). Użyj ustawień domyślnych.
1. Na karcie **Klastry obliczeniowe** wybierz opcję **Nowe**, aby otworzyć kreatora, który pomoże Ci utworzyć nowy klaster obliczeniowy. Postępuj zgodnie z instrukcjami wyświetlanymi na ekranie. Klaster obliczeniowy będzie używany do generowania prognoz popytu. Jego ustawienia wpływają na wydajność i maksymalny poziom równoległości uruchamiania. Ustaw następujące pola, ale użyj ustawień domyślnych dla wszystkich innych pól:

    - **Nazwa** — wprowadź *e2ecpucluster*.
    - **Rozmiar maszyny wirtualnej** — dostosuj to ustawienie zgodnie z woluminem danych, które mają być wykorzystywane jako dane wejściowe do prognozowania popytu. Liczba węzłów nie powinna przekraczać 11, ponieważ jeden węzeł jest wymagany do wyzwalania generowania prognozy popytu, a maksymalna liczba węzłów, których można następnie użyć do wygenerowania prognozy, wynosi 10. (Liczbę węzłów ustawia się także w pliku parameters.py w sekcji [Krok 5. Tworzenie potoków](#create-pipelines)). W każdym węźle będzie kilka procesów roboczych, które równolegle uruchamiają skrypty prognozowania. Łączna liczba procesów roboczych w tym zadaniu będzie *liczbą rdzeni węzła* × *liczba węzłów*. Na przykład, jeśli klaster obliczeniowy ma typ *Standard\_D4* (osiem rdzeni) i maksymalnie 11 węzłów, a w pliku parameters.py wartość `nodes_count` wynosi *10*, efektywny poziom równoległości wynosi 80.

##### <a name="step-5-create-pipelines"></a><a name="create-pipelines"></a>Krok 5. Tworzenie potoków

Potoki stanowią sposób uruchamiania skryptów prognozowania z aplikacji Supply Chain Management. Poniższa procedura umożliwia tworzenie wymaganych potoków.

1. W witrynie GitHub otwórz [szablony prognozowania popytu aplikacji Dynamics 365 Supply Chain Management za pomocą repozytorium usługi Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) i pobierz następujące pliki:

    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. W programie Azure Machine Learning Studio wybierz w nawigatorze pozycję **Notebooks**.
1. W strukturze **plików** znajdź następującą lokalizację: **\[Users/bieżący użytkownik\]/src**.
1. Przekaż cztery pliki pobrane w kroku 1 do lokalizacji znalezionej w poprzednim kroku.
1. Na platformie Azure otwórz i przejrzyj właśnie przekazany plik **parameters.py**, który właśnie został przekazany. Upewnij się, że wartość `nodes_count` jest o jeden mniejsza niż wartość skonfigurowana dla klastra obliczeniowego w sekcji [Krok 4. Konfigurowanie zasobów obliczeniowych](#config-compute-resources). Jeśli wartość `nodes_count` jest większa lub równa liczbie węzłów w klastrze obliczeniowym, uruchamianie przebiegu potoku może okazać się możliwe. Natomiast później podczas oczekiwania na wymagane zasoby przestanie on reagować. Aby uzyskać więcej informacji na temat liczby węzłów, zobacz sekcję [Krok 4. Konfigurowanie zasobów obliczeniowych](#config-compute-resources).
1. Wybierz właśnie przekazany plik **api_trigger.py** i uruchom go. Spowoduje to utworzenie potoku, który może być wyzwalany przez interfejs API.

### <a name="set-up-a-new-active-directory-application"></a><a name="aad-app"></a>Konfigurowanie nowej aplikacji usługi Active Directory

Aplikacja usługi Active Directory jest wymagana do uwierzytelnienia w przypadku zasobów dedykowanych do prognozowania popytu przy użyciu jednostki usługi. W związku z tym aplikacja powinna mieć najniższy poziom uprawnień, który jest wymagany do wygenerowania prognozy.

1. Zaloguj się do witryny Azure Portal.
1. Zarejestruj nową aplikację w usłudze Azure Active Directory (Azure AD) dzierżawcy. Instrukcje można znaleźć w części [Korzystanie z portalu do tworzenia aplikacji usługi i jednostki usługi Azure AD, która może uzyskiwać dostęp do zasobów](/azure/active-directory/develop/howto-create-service-principal-portal).
1. Dokończ pracę z kreatorem, wykonując instrukcje wyświetlane na ekranie. Użyj ustawień domyślnych.
1. Przyznaj nowej aplikacji usługi Active Directory dostęp do następujących zasobów utworzonych w sekcji [Konfigurowanie uczenia maszynowego na platformie Azure](#ml-workspace). Aby uzyskać instrukcje, zobacz temat [Przypisywanie ról platformy Azure za pomocą witryny Azure Portal](/azure/role-based-access-control/role-assignments-portal?tabs=current). Ten krok umożliwi systemowi importowanie i eksportowanie danych prognozowania oraz wyzwalanie przebiegów potoków z poziomu aplikacji Supply Chain Management.

    - Rola współautora w obszarze roboczym usługi Machine Learning
    - Rola współautora do dedykowanego konta magazynu
    - Rola współautora danych obiektów blob magazynu do dedykowanego konta magazynu

1. W sekcji **Certyfikaty i wpisy tajne** w utworzonej aplikacji utwórz wpis tajny dla aplikacji. Aby uzyskać instrukcje, zobacz temat [Dodawanie klucza tajnego klienta](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).
1. Zanotuj identyfikator aplikacji i jej wpis tajny. Szczegóły tej aplikacji będą Ci potrzebne później, po skonfigurowaniu strony **Parametry prognozowania popytu** w aplikacji Supply Chain Management.

### <a name="set-up-azure-machine-learning-service-connection-parameters-in-supply-chain-management"></a><a name="demand-forecast-parameters"></a>Konfigurowanie parametrów połączenia usługi Azure Machine Learning Service w aplikacji Supply Chain Management

Poniższa procedura służy do łączenia środowiska aplikacji Supply Chain Management z usługą Machine Learning właśnie skonfigurowaną na platformie Azure.

1. Zaloguj się do modułu Supply Chain Management.
1. Wybierz kolejno opcje **Planowanie główne \> Ustawienia \> Prognozowanie popytu \> Parametry prognozowania popytu**.
1. Na karcie **Ogólne** upewnij się, że w polu **Strategia generowania prognozy** jest ustawiona na *Azure Machine Learning Service*.
1. Na karcie **Klucze alokacji pozycji** upewnij się, że w polu **Strategia generowania prognozy** jest ustawiona opcja *Azure Machine Learning Service* dla każdego klucza alokacji, który powinien używać usługi Azure Machine Learning Service do prognozowania popytu.
1. Na karcie **Azure Machine Learning Service** ustaw następujące pola:

    - **Identyfikator dzierżawcy** — wprowadź identyfikator dzierżawcy platformy Azure. Aplikacja Supply Chain Management użyje tego identyfikatora do uwierzytelniania w usłudze Azure Machine Learning Service. Możesz znaleźć swój identyfikator dzierżawcy na stronie **Przegląd** dla usługi Azure AD w witrynie Azure Portal.
    - **Identyfikator aplikacji jednostki usługi** — wprowadź identyfikator aplikacji utworzonej w sekcji [Aplikacja usługi Active Directory](#aad-app). Ta wartość służy do autoryzowania żądań interfejsu API w usłudze Azure Machine Learning Service.
    - **Wpis tajny jednostki usługi** — wprowadź wpis tajny aplikacji jednostki usługi utworzonej w sekcji [Aplikacja usługi Active Directory](#aad-app). Ta wartość służy do nabywania tokenu dostępu dla podmiotu zabezpieczeń utworzonego w celu wykonywania autoryzowanych operacji w usłudze Azure Storage i obszarze roboczym usługi Azure Machine Language.
    - **Nazwa konta magazynu** — wprowadź nazwę konta magazynu platformy Azure, która jest określona podczas pracy z kreatorem instalacji w obszarze roboczym platformy Azure. (Więcej informacji zawiera sekcja [Konfigurowanie uczenia maszynowego na platformie Azure](#ml-workspace)).
    - **Adres punktu końcowego potoku** — wprowadź adres URL punktu końcowego REST potoku dla usługi Azure Machine Learning Service. Ten potok został utworzony w ostatnim kroku [konfigurowania usługi Machine Learning na platformie Azure](#ml-workspace). Aby uzyskać adres URL potoku, zaloguj się do witryny Azure Portal, wybierz pozycję **Potoki** w obszarze nawigacji. Na karcie **Potok** wybierz punkt końcowy potoku o nazwie **TriggerDemandForecastGeneration**. Następnie skopiuj wyświetlony punkt końcowy REST.

    ![Parametry na karcie Azure Machine Learning Service strony Parametry prognozowania popytu.](media/azure-ml-service-parameters.png "Parametry na karcie Azure Machine Learning Service strony Parametry prognozowania popytu")

## <a name="privacy-notice"></a><a name="privacy"></a>Klauzula prywatności

Po wybraniu usługi *Azure Machine Learning Service* jako strategii generowania prognozy aplikacja Supply Chain Management automatycznie wysyła dane klientów dotyczące popytu historycznego, takie jak agregowane ilości, nazwy i wymiary produktów, lokalizacje wysyłki i odbioru, identyfikatory klientów, a także parametry prognozy, do regionu geograficznego, w którym znajduje się obszar roboczy usługi Machine Learning i jego połączone konto magazynu, w celu prognozowania przyszłego popytu. Usługa Azure Machine Learning Service może znajdować się w innym regionie geograficznym niż region, w którym rozmieszczono aplikację Supply Chain Management. Niektórzy użytkownicy mogą kontrolować, czy ta funkcja jest włączona, wybierając strategię generowania prognozy na stronie **Parametry prognozowania popytu**.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie prognozowania popytu](introduction-demand-forecasting.md)
- [Generowanie bazowej prognozy statystycznej](generate-statistical-baseline-forecast.md)
- [Wprowadzanie ręcznych korekt prognozy bazowej](manual-adjustments-baseline-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
