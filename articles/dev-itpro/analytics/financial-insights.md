---
title: "Szczegółowe dane finansowe"
description: "Wykorzystując usługę Microsoft Power BI, obszar roboczy Szczegółowe dane finansowe zbiera w jednym miejscu kluczowe wskaźniki wydajności (KPI) dotyczące finansów, wykresy i sprawozdania finansowe."
author: kweekley
manager: AnnBe
ms.date: 01/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 8075abccdcdde21df967dcc9948a738895f35cef
ms.openlocfilehash: 3da5344ec6edec0af28aa21d45af962307231e67
ms.contentlocale: pl-pl
ms.lasthandoff: 01/25/2018

---

# <a name="financial-insights"></a>Szczegółowe dane finansowe

[!include[banner](../includes/banner.md)]

Wykorzystując usługę Microsoft Power BI, obszar roboczy **Szczegółowe dane finansowe** zbiera w jednym miejscu kluczowe wskaźniki wydajności (KPI) dotyczące finansów, wykresy i sprawozdania finansowe. Usługa Power BI jest wbudowana w rozwiązaniu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.
Obszar roboczy **Szczegółowe dane finansowe** koncentruje się na sprawozdawczości analitycznej. Osoby z całej organizacji mogą wyświetlać, badać i poznawać informacje oraz działać na ich podstawie. 

Obszar roboczy **Szczegółowe dane finansowe** łączy dane z księgi głównej i ksiąg podrzędnych, tworząc bardziej kompletny obraz kondycji finansowej organizacji.

> [!NOTE] 
> Ten dokument wykorzystuje następującą terminologię usługi Power BI:                                                                           
**Raport** — jeden plik .pbix, w którym są zapisywane wszystkie elementy wizualne ze wszystkich kart.                                                          
**Strona** — karta w jednym pliku .pbix. Każda strona może zawierać jeden lub więcej elementów wizualnych.                                                     
**Element wizualny** — jedno źródło danych, takie jak karta, wskaźnik KPI, wykres, graf, macierz lub sprawozdanie finansowe. Strona, na której elementem wizualnym jest sprawozdanie finansowe, nie może zawierać żadnych innych elementów wizualnych, co wynika z rozmiaru danych stanowiących podstawę raportu.


Obecnie obszar roboczy **Szczegółowe dane finansowe** służy do wyświetlania danych aktywnej firmy lub wszystkich firm. W przyszłych wersjach obszar roboczy zmieni się w miejsce, gdzie za pomocą usługi Power BI będzie można edytować i tworzyć elementy wizualne.

Obszar roboczy **Przegląd dla dyrektora finansowego** zawiera te same elementy wizualne, co obszar roboczy **Szczegółowe dane finansowe**, ale koncentruje się na możliwości wyświetlania i filtrowania danych w istniejących raportach. W przyszłych wersjach będzie można dodawać nowe elementy wizualne do obszaru roboczego **Szczegółowe dane finansowe**. Nowe elementy wizualne mogą być również dostępne w obszarach roboczych ukierunkowanych na inne role, takie jak menedżerowie projektów i menedżerowie ds. rozrachunków z dostawcami. Obszar roboczy **Przegląd dla dyrektora finansowego** nadal pokazuje dane ze wszystkich firm, niezależnie od tego, do których firm rola ma dostęp.

## <a name="finance-and-operations-setup"></a>Konfiguracja w programie Finance and Operations
**Księga główna**

Typ konta głównego i kategorie kont głównych służą do wypełniania odpowiednich domyślnych kont głównych w sprawozdaniu finansowym **Bilans** oraz różnych sprawozdaniach finansowych **Rachunek zysków i strat** w obszarze roboczym **Szczegółowe dane finansowe**.

Na stronie **Konta główne** należy zdefiniować konto główne, przypisując mu jeden z następujących typów:

•   Przychody

•   Wydatki

•   Aktywa

•   Zobowiązania

•   Kapitał własny

Nie przypisuj swoim kontom głównym żadnego innego typu, takiego jak **Bilans** czy **Rachunek zysków i strat**. Jeśli zostaną przypisane inne typy konta głównego, aparat sprawozdawczości nie będzie mógł ich rozpoznać, ponieważ te typy nie są wystarczająco szczegółowe. Typ konta głównego musi być rozpoznawany, aby zobowiązania i przychody były wyświetlane jako kwoty dodatnie w raportach finansowych.

Aby konto główne było wyświetlane w sprawozdaniach finansowych i uwzględniane w różnych innych elementach wizualnych, takich jak kluczowe wskaźniki wydajności, musi mieć przypisaną kategorię konta głównego. Funkcjonalność kategorii kont głównych została udoskonalona i teraz zawiera parametr kolejności wyświetlania. Kolejność wyświetlania jest używana w szczególności w sprawozdaniach finansowych w obszarze roboczym **Szczegółowe dane finansowe**. Po zmodyfikowaniu istniejącej lub dodaniu nowej kategorii konta głównego można zmienić wartość pola **Kolejność wyświetlania**, aby określić kolejność, w jakiej kategorie kont głównych powinny być wyświetlane w sprawozdaniu finansowym. Jeśli trzeba zmienić kolejność wyświetlania wielu kategorii kont głównych, można użyć funkcji Otwórz w programie Excel i szybko zmodyfikować zmiany oraz je opublikować w programie Finance and Operations.


## <a name="entity-store"></a>Magazyn jednostek
Dane obszaru roboczego **Szczegółowe dane finansowe** są pobierane z magazynu jednostek (**Administrowanie systemem** > **Ustawienia** > **Magazyn jednostek**). Jeśli po otwarciu obszaru roboczego **Przegląd dla dyrektora finansowego** lub **Szczegółowe dane finansowe** na elementach wizualnych pojawi się komunikat ostrzegawczy podany niżej, należy zaktualizować jednostki.
 
![Ostrzeżenie](./media/Cantdisplay.png)

Należy zaktualizować następujące jednostki, aby widzieć dane w obszarach roboczych **Szczegółowe dane finansowe** i **Przegląd dla dyrektora finansowego**:

•   CustCollectionsBIMeasurements

•   FinancialReportingOtherData

•   FinancialReportingReferenceData

•   FinancialReportingTransactionData

•   LedgerCovLiquidityMeasurement

•   Moduł Zakupy

•   Moduł Sprzedaż

W poprzedniej wersji dane w obszarze roboczym **Przegląd dla dyrektora finansowego** korzystały z jednostek LedgerActivityMeasure i VendPaymentBIMeasure. W bieżącej wersji te jednostki nie są już używane.

Istnieje możliwość zdefiniowania cyklicznego zadania wsadowego do regularnej aktualizacji danych w jednostkach. Ponieważ podczas aktualizacji każda jednostka jest całkowicie odbudowywana, należy ostrożnie wybierać czas i częstotliwość aktualizacji jednostek. Podstawową jednostką używaną przy sporządzaniu sprawozdaniach finansowych jest FinancialReportingTransactionData. W związku z tym można zdecydować, że ma być aktualizowana częściej.

## <a name="security"></a>Zabezpieczenia
Obecnie dane w osadzonych raportach usługi Power BI nie mogą się ograniczać do firm, wobec których użytkownik ma dostęp. W związku z tym wbudowane raporty usługi Power BI są kontrolowane za pomocą obowiązków w konfiguracji zabezpieczeń. Zdefiniowane obowiązki umożliwiają dostęp do danych wszystkich firm lub tylko aktywnej firmy. W poniższej tabeli przedstawiono istniejące obowiązki oraz role, do których są one przypisane. Obowiązki można usuwać i przypisywać do różnych ról zgodnie z potrzebami organizacji.

| **Obowiązek**                     | **Role**                                       | Opis                     |
|------------------------------|-------------------------------------------------|-----------------|
| Wyświetlanie obszaru roboczego Dyrektor finansowy — przegląd  | Dyrektor finansowy                         | •    Ten obowiązek umożliwia dostęp do obszaru roboczego Przegląd dla dyrektora finansowego. • Domyślnie jako filtr jest używana aktywna firma. Można jednak dodać wszystkie firmy, niezależnie od tego, czy użytkownik ma dostęp do innych firm.               |
| Wyświetlanie szczegółowych danych finansowych bieżącej firmy | •   Księgowy •    Kierownik ds. księgowania •    Kierownik ds. księgowania • Audytor •   Menedżer budżetu •    Dyrektor naczelny •   Dyrektor finansowy •   Kontroler finansowy  |   • Ten obowiązek umożliwia dostęp do obszaru roboczego Szczegółowe dane finansowe. • Domyślnie jako filtr jest używana aktywna firma. Nie można dodać innych firm.            |
| Wyświetlanie międzyfirmowych szczegółowych danych finansowych   | •   W rozwiązaniu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition wer. 7.3 ten obowiązek nie jest przypisany do roli. • W następnej wersji ten obowiązek będzie przypisany do roli Dyrektor finansowy. | •    Ten obowiązek umożliwia dostęp do menu obszaru roboczego Przegląd dla dyrektora finansowego. •    Domyślnie jako filtr jest używana aktywna firma. Można jednak dodać wszystkie firmy, niezależnie od tego, czy użytkownik ma dostęp do innych firm.             |


## <a name="how-financial-statements-work"></a>Zasada działania sprawozdań finansowych
Mimo iż obszar roboczy **Szczegółowe dane finansowe** zawiera sprawozdania finansowe, nie zastępuje modułu Raporty finansowe w programie Finance and Operations. Domyślne sprawozdania finansowe w obszarze roboczym **Szczegółowe dane finansowe** mają ograniczony zakres i nie obejmują wszystkich typów sprawozdań finansowych. Raporty finansowe to nadal podstawowe narzędzie do projektowania, tworzenia i generowania ustawowych sprawozdań finansowych.

Oprócz elementów wizualnych z oryginalnego obszaru roboczego **Przegląd dla dyrektora finansowego** są teraz dostępne nowe kluczowe wskaźniki wydajności, wykresy i sprawozdania finansowe. Dostępne są następujące sprawozdania finansowe:

•   Bilans próbny

•   Bilans

•   Rachunku zysków i strat według regionów

•   Rachunek strat i zysków — wartości rzeczywiste a budżet

•   Rachunek zysków i strat z odchyleniami

•   Rachunek zysków i strat — trend 12-miesięczny

•   Wydatki — trend trzyletni

•   Wydatki według dostawców

•   Sprzedaż według odbiorców

## <a name="edit-visuals"></a>Edytowanie elementów wizualnych
W pierwszej wersji obszaru roboczego **Szczegółowe dane finansowe** nie można edytować żadnych elementów wizualnych. W przyszłych wersjach użytkownicy mający odpowiednie zabezpieczenie będą mogli tworzyć nowe elementy wizualne, kopiować istniejące elementy wizualne oraz edytować elementy wizualne. Mimo że pliki .pbix zawierające raporty są dostępne jako zasoby, nie zalecamy edytowania domyślnych raportów. Dodatkowe zmiany zostaną wprowadzone w obiektach używanych do tworzenia sprawozdań finansowych: modelu danych, raportach domyślnych i elemencie wizualnym niestandardowych sprawozdań finansowych. W związku z tym aby korzystać z nowych funkcji i zmian w modelu danych wprowadzonych w następnej wersji, należałoby ponownie wprowadzić wszystkie zmiany dokonane w domyślnych raportach za pomocą aplikacji Microsoft Power BI pulpitu.


## <a name="filtering"></a>Filtrowanie
Użytkownicy mogą filtrować raport przy użyciu okienka **Filtr** po lewej stronie. Jest to to samo okienko, jak dostępne w aplikacji Power BI Desktop.
Istnieją różne poziomy filtrowania. Niektóre z nich mogą być niedostępne, w zależności od tego, co wybrano na stronie (karcie) i czy są używane funkcje drążenia wskroś:

•   **Filtry poziomu raportu** — te filtry są stosowane do wszystkich elementów wizualnych na wszystkich stronach (kartach).

•   **Filtry poziomu strony** — te filtry są stosowane do wszystkich elementów wizualnych na aktywnej karcie. Są nakładane na filtry poziomu raportu.

•   **Filtry poziomu elementu wizualnego** — te filtry są stosowane tylko do wybranego elementu wizualnego. Są nakładane na filtry poziomu strony.

•   **Filtr drążenia wskroś** — ten filtr filtruje od zastosowanego „źródłowego” elementu wizualnego do bieżącego elementu wizualnego podczas drążenia wskroś od źródłowego elementu wizualnego do bieżącego elementu wizualnego.

![Filtr](./media/filter.png)


Aby usunąć wartość określonego filtru, wybierz symbol gumki obok tego filtru. Nie usuwaj filtru naciśnięciem przycisku X. Jeśli wybierzesz symbol X, pole, według którego odbywa się filtrowanie, zostanie usunięte jako opcja filtru. Jeśli przypadkowo usuniesz pole z filtru, zamknij obszar roboczy, a następnie otwórz go ponownie. Zostaną wtedy ponownie zastosowane domyślne ustawienia filtru.

Domyślnie przy pierwszym otwarciu obszarów roboczych aktywna firma jest używana jako filtr poziomu raportu. W zależności od ich zabezpieczeń użytkownicy mogą być w stanie dodać inne firmy lub zmienić domyślną firmę zaznaczoną w filtrze.

Filtr **Kalendarz obrachunkowy** jest wymagany do używania poprawnego kalendarz dla elementu wizualnego. Domyślnie filtrem poziomu raportu jest kalendarz obrachunkowy aktywnej firmy. Jeśli filtr zostanie zmieniony na kalendarz obrachunkowy mający inną datę rozpoczęcia lub zakończenia, salda początkowe nie zostaną uwzględnione. W związku z tym sprawozdanie finansowe **Bilans** nie będzie zawierać poprawnych sald. Jeśli wybierzesz dodatkowy kalendarz obrachunkowy w filtrze, zobaczysz dodatkowy zestaw kolumn. Każdy dodatkowy zestaw kolumn pokazuje kwoty dla innego kalendarza obrachunkowego.

Jest także wymagany filtr **Warstwa księgowania**. Domyślnie jest ustawiony filtr Bieżący. W filtrze można wybrać dodatkowe warstwy księgowania, aby wyświetlać kwoty łączne.

Filtry są również dostępne dla pól **Data** i **Rok obrachunkowy**. Zazwyczaj te filtry są stosowane na poziomie strony. Domyślnie filtr **Data** korzysta z daty relacyjnej, którą można zmienić. Można również usunąć filtr daty relacyjnej i zamiast niego używać filtru **Rok obrachunkowy**.

## <a name="currency"></a>Waluta

Wszystkie elementy wizualne, które przedstawiają raporty na podstawie danych księgi głównej, pokazują kwoty w walucie rozliczeniowej. W związku z tym podczas filtrowania według firmy należy uważać, aby uwzględnić tylko firmy, które mają taką samą walutę rozliczeniową. W przeciwnym razie zostaną zagregowane dane w różnych walutach.

Wszystkie elementy wizualne, które przedstawiają raporty na podstawie danych księgi podrzędnej, takie jak **Prognoza przepływów pieniężnych** i **10 najlepszych**, pokazują kwoty w walucie systemowej. Waluta systemowa i systemowy typ kursu wymiany są definiowane na stronie **Parametry systemowe**.

Element wizualny **Saldo wg konta bankowego** używa kwot w walucie konta bankowego.

## <a name="dimensions"></a>Wymiary

Domyślne sprawozdania finansowe nie zawierają żadnych wymiarów finansowych, ale skupiają się wyłącznie na koncie głównym. Obsługa wymiarów finansowych będzie dostępna w przyszłych wersjach, gdy będzie można edytować raporty. Wtedy będzie można filtrować według wartości wymiarów finansowych.

Niektóre sprawozdania finansowe zawierają wymiary oparte na transakcjach w księgach podrzędnych. Celem nowych sprawozdań finansowych jest umożliwienie filtrowania według wymiarów, które nie są skonfigurowane jako wymiary finansowe. Na przykład domyślny raport Wydatki według dostawców pozwala analizować bardziej szczegółowo niż poziom konta głównego i zobaczyć salda z podziałem na dostawców. Dostawca nie jest skonfigurowany jako wymiar finansowy. Zamiast tego system wraca do pierwotnej transakcji w księdze podrzędnej, aby znaleźć dostawcę.

W raportach domyślnych są używane następujące wymiary. Żaden z tych wymiarów nie jest wymiarem finansowym.

•   Dostawca

•   Grupa dostawców

•   Odbiorca

•   Grupa odbiorców

•   Kraj/region

•   Województwo

•   Miejscowość

> [!IMPORTANT] 
> Jeśli zsumujesz transakcje dla wielu dostawców lub odbiorców w jednym załączniku przy użyciu arkuszy finansowych, dane będą błędne. Aparat sprawozdawczości nie może ustalić, który dostawca lub odbiorca jest powiązany z konkretnym kontem księgowym we wpisie w arkuszu, ponieważ te informacje nie są nigdzie przechowywane. Z tego względu nie zalecamy wprowadzania wielu dostawców, odbiorców, środków trwałych ani projektów w jednym załączniku.

## <a name="drill-on-data"></a>Przechodzenie do szczegółów danych

W usłudze Power BI jest dostępnych kilka poziomów przechodzenia do szczegółów (drążenia). Każdy poziom ma inną nazwą i inne funkcje. Można również przechodzić do szczegółów wierszy i kolumn. W tym punkcie omówiono różne dostępne opcje, używając sprawozdania finansowego **Bilans próbny** jako przykładu ilustrującego drążenie w wierszach. Te same funkcje istnieją dla kolumn. Wystarczy tylko zmienić wartość ustawienia **Wyszczególnij według**.

Na poniższej ilustracji sprawozdanie **Bilans próbny** jest zwinięte do najwyższego poziomu w hierarchii wierszy, czyli do typu konta głównego.

![Bilans próbny](./media/trial-balance.png)

 
Aby wyświetlić następny poziom hierarchii, czyli kategorie konta głównego, można w polu **Wyszczególnij według** ustawić opcję **Wiersze**, a następnie nacisnąć przycisk **Rozwiń** (trzeci przycisk za polem Wyszczególnij według). Teraz zobaczysz rozwinięte wszystkie kategorie konta głównego. Obecnie usługa Power BI nie pozwala rozwinąć tylko jednego wiersza lub kolumny, ale nadal widzieć wszystkie pozostałe wiersze lub kolumny.
 
![Bilans próbny](./media/trial-balance2.png)
 
  
Aby rozwinąć do poziomu kont głównych dla wszystkich wierszy, ponownie użyj przycisku **Rozwiń**. Jednak aby uszczegółowić do kont głównych tylko dla jednego wiersza, najpierw wybierz przycisk **Przejdź do szczegółów** (pojedynczą strzałkę skierowaną w dół po prawej stronie okna), a następnie wybierz wiersz, który chcesz uszczegółowić. Na poniższej ilustracji przedstawiono wynik zaznaczenia wiersza **Sprzedaż** po naciśnięciu przycisku **Przejdź do szczegółów**.

![Bilans próbny](./media/trial-balance3.png)

Po przejściu do szczegółów w jednym wierszu trzeba kliknąć kilka razy, aby wrócić do pełnego bilansu próbnego. Przycisk **Uogólnij** (pierwszy za polem **Wyszczególnij według**) powoduje uogólnianie tylko w kontekście kategorii **Sprzedaż**, jak pokazano na poniższej ilustracji.
 
![Bilans próbny](./media/trial-balance4.png)
 
 
Można dalej klikać przycisk **Uogólnij**, aby wrócić do najwyższego poziomu podsumowania dla wierszy.

W oknie usługi Power BI znajduje się również przycisk, który umożliwia przejście do następnego poziomu w hierarchii (drugi przycisk za polem **Wyszczególnij według**). Efekt użycia tego przycisku różni się od działania przycisku **Rozwiń** (trzeci przycisk za polem **Wyszczególnij według**), który służy do rozwijania hierarchii. Po rozwinięciu hierarchii pozostaje ona w raporcie. Na przykład, jak pokazano wcześniej, jeśli rozwiniesz poziom typu konta głównego, będzie on widoczny w raporcie. Jednak po przejściu do następnego poziomu w hierarchii raport nie będzie już pokazywał obiektu nadrzędnego w hierarchii, jak przestawiono na ilustracji poniżej.

![Bilans próbny](./media/trial-balance5.png)

 
Aby zobaczyć szczegóły transakcji stojących za zbiorczymi saldami, można wybrać pewne kwoty i w ten sposób przejść z powrotem do programu Finance and Operations.

Drążenie wstecz ze sprawozdań finansowych powoduje przejście do Eksploratora źródeł księgowania (ASE), a nie do transakcji w załącznikach. Edytor ASE nie pokazuje wyłącznie zapisów księgowych istniejących w księdze głównej. Zamiast tego przedstawia szczegóły transakcji z księgi podrzędnej. W związku z tym otrzymujesz znacznie więcej informacji na temat transakcji źródłowej i można ich używać do analizy. Na przykład widać, kto był dostawcą lub odbiorcą, co odbiorca kupił lub sprzedawca sprzedał, a nawet którego projektu dotyczyła transakcja.

Wartości następujących filtrów są wysyłane ze sprawozdań finansowych do edytora ASE, dzięki czemu edytor ASE pokazuje zagregowane transakcje:

Pola wymagane do filtrowania:

  - Firma
 
  - Kalendarz obrachunkowy
 
  - Rok
 
  - Identyfikator konta głównego

Pola opcjonalne w filtrowaniu:

  - Kwartał

  - Miesiąc

  - Okres

Jeśli nie rozwiniesz wiersza do odpowiednio niskiego poziomu, przechodzenie do szczegółów nie zadziała. Na przykład jeśli rozwiniesz w dół tylko do kategorii konta głównego, w edytorze ASE nie można wykonać drążenia w dół do salda, ponieważ do filtrowania w edytorze ASE jest wymagane pole konta głównego.

Jeśli rozwiniesz wiersz za bardzo do dołu, wartości dodatkowych filtrów nie są wysyłane ze sprawozdań finansowych do edytora ASE. W efekcie mogą się pojawić inne liczby. Na przykład jeśli rozwiniesz w dół do kraju lub regionu w wierszach sprawozdania finansowego Rachunku zysków i strat według regionów, kraj lub region nie będzie uwzględniany jako filtr w edytorze ASE.

> [!NOTE]
> Można przechodzić do kolejnych poziomów szczegółów w wierszach i kolumnach sprawozdania finansowego, których filtrowanie obecnie obsługuje edytor ASE. W związku z tym w pewnych sytuacjach suma szczegółowych transakcji w edytorze ASE nie będzie równa saldu wyświetlanemu podczas drążenia wstecz. Ta funkcja będzie nadal udoskonalana w przyszłości.

## <a name="hierarchies"></a>Hierarchie

Domyślne sprawozdania finansowe wykorzystują dwie hierarchie do drążenia i rozwijania danych. Jedna hierarchia jest przeznaczona dla wierszy, a druga dla kolumn. Obie hierarchie są wstępnie zdefiniowane w projekcie sprawozdania finansowego. W większości sprawozdań finansowych hierarchia wiersza ma postać **Typ konta głównego** > **Kategorie kont głównych** > **Konto główne**. Jednak niektóre raporty mają dodatkowe pola, takie jak Kraj i Region. Dodatkowe węzły w hierarchii bazują na danych z księgi podrzędnej dla każdej transakcji.

W przypadku kolumn hierarchia koncentruje się na firmach i okresach obrachunkowych. W większości sprawozdań finansowych hierarchia kolumny ma postać **Firma** > **Kalendarz obrachunkowy** > **Roku obrachunkowy** > **Kwartał** > **Okres**.

Obecnie sprawozdania finansowe nie obsługują hierarchii organizacyjnych, które pozwalają agregować dane.

## <a name="data-limitations"></a>Ograniczenia dotyczące danych
Elementy wizualne sprawozdania finansowego mają zdefiniowane ograniczenie liczby wierszy, które mogą być pokazywane. Obecnie limit jest równy 30 000. Po przekroczeniu tego limitu na elemencie graficznym pojawi się symbol ostrzeżenia informujący o zaistniałej sytuacji.
 
![Ograniczenia dotyczące danych](./media/data-limit.png)


Jeśli ten maksymalny limit zostanie przekroczony, sumy wyświetlane w sprawozdaniu finansowym będą nieprawidłowe, ponieważ nie wszystkie wiersze zostały załadowane do elementu wizualnego.

### <a name="empty-rows"></a>Puste wiersze
Usługa Power BI nie oferuje opcji ukrywania i wyświetlania pustych wierszy. Jeśli wiersz nie ma żadnych danych, nie będzie widoczny w elemencie wizualnym.

## <a name="what-is-coming-in-future-releases"></a>Co się pojawi w przyszłych wersjach?
Cały czas będą udoskonalane nowe obszary robocze i sprawozdania finansowe korzystające z usługi Power BI. Poniżej przedstawiono kilka nowych funkcji, które są rozważane dla przyszłych wersji:

 - Możliwość kopiowania, edytowania, usuwania i tworzenia elementów wizualnych, a nawet sprawozdań finansowych                                                  
 - Dodatkowe domyślne raporty                                                                                                            
    - Obsługa dodatkowych danych księgi podrzędnej                                                                                            
 - Obsługa waluty raportowania                                                                                                      
 - Dodawanie niestandardowych obliczeń dla wierszy i kolumn                                                                                          
 - Możliwość eksportowania sprawozdań finansowych do programu Microsoft Excel                                                                     
   - Zachowanie formatu sprawozdania finansowego podczas eksportu                                                                          
   - Analizowanie danych w programie Excel przez utworzenie tabeli przestawnej, która korzysta z informacji zawartych w elemencie graficznym                                              
 - Obsługa ustawień regionalnych                                                                                                                        
 - Możliwość definiowanie hierarchii raportowania, co pozwoli zdefiniować hierarchie kont głównych lub hierarchię organizacyjną, których można używać w sprawozdaniach finansowych do projektowania, filtrowania i zabezpieczania                                                                    
 - Obsługa drukowania

Informacje o nowych funkcjach będą przekazywane w witrynie sieci Web planu rozwoju z momencie rozpoczęcia prac: https://roadmap.dynamics.com/.

## <a name="additional-resources-for-power-bi"></a>Dodatkowe zasoby dla usługi Power BI

Informacje zawarte w poniższych materiałach nie są wymagane, aby można było używać osadzonych raportów w obszarach roboczych **Przegląd dla dyrektora finansowego** i **Szczegółowe dane finansowe** w środowisku produkcyjnym. Przydają się jedynie do środowisk programistycznych oraz jeśli chcesz osadzać własne raporty usługi Power BI w programie Finance and Operations.

https://blogs.msdn.microsoft.com/dynamicsaxbi/2017/07/29/accessing-analytical-workspaces-on-1box-environment/

https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/add-analytics-tab-workspaces
