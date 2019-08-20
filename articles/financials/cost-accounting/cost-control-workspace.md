---
title: Obszar roboczy kontroli kosztów
description: Ten temat zawiera informacje dotyczące obszaru roboczego Kontrola kosztów. Ten obszar roboczy jest centralnym miejscem, w którym menedżerowie odpowiedzialni za kontrolę obiektu kosztów lub zbioru obiektów kosztów w granicach wymiaru lub między wymiarami mają dostęp do raportów.
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostControlWorkspaceConfiguration, CAMCostControlWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 82eb312d534a43d48be2dabbf9f9ae3e32545bac
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841664"
---
# <a name="cost-control-overview"></a>Omówienie obszaru roboczego Kontrola kosztów 

[!include [banner](../includes/banner.md)]

Obszar roboczy **Kontrola kosztów** jest centralnym miejscem, w którym menedżerowie odpowiedzialni za kontrolę obiektu kosztów lub zbioru obiektów kosztów w granicach wymiaru lub między wymiarami (np. w centrach kosztów i grupach produktów) mają dostęp do raportów. Raporty w obszarze roboczym są w pełni zarządzane przez księgowych kosztów, dzięki czemu układ i dane używane w raportach mogą być spójne w całej organizacji.

## <a name="cost-control-workspace-configuration"></a>Konfiguracja obszaru roboczego Kontrola kosztów

Księgowi kosztów mogą zdefiniować dowolną liczbę konfiguracji raportów, jakiej potrzebują dla żądanej kompozycji danych lub układu. Konfiguracja raportu składa się z sześciu sekcji. Każda sekcja ma pewien udział w wybieraniu docelowej kompozycji danych lub układu.

Aby skonfigurować obszar roboczy kontroli kosztów, kliknij kolejno opcje **Rachunek kosztów** \> **Ustawienia** \> **Konfiguracja obszaru roboczego Kontrola kosztów**.

### <a name="general"></a>Ogólne

Na skróconej karcie **Ogólne** można utworzyć unikatowy układ raportu. Nazwa raportu będzie unikatowym identyfikatorem, który użytkownicy będą mogli rozpoznać w obszarze roboczym **Kontrola kosztów**. Można również określić, czy raport powinien być udostępniany, czy też przechowywany wewnętrznie tylko dla księgowych kosztów.

| Pole       | opis |
|-------------|-------------|
| Nazwisko        | Wprowadź unikatową nazwę układu. |
| opis | Wprowadź szczegółowy opis. |
| Opublikowane   | Jeśli w tym polu zostanie ustawiona wartość **Tak**, użytkownik, któremu przypisano jedną z następujących ról, może wyświetlać raport w obszarze roboczym **Kontrola kosztów**:<ul><li>Menedżer rachunku kosztów</li><li>Księgowy kosztów</li><li>Księgowy rachunku kosztów</li><li>Kontroler obiektów kosztów</li></ul>Jeśli w tym polu zostanie ustawiona wartość **Nie**, tylko użytkownicy, którym przypisano jedną z następujących ról, mogą wyświetlać raport w obszarze roboczym **Kontrola kosztów**:<ul><li>Menedżer rachunku kosztów</li><li>Księgowy kosztów</li><li>Księgowy rachunku kosztów</li></ul> |

### <a name="data-filtering"></a>Filtrowanie danych

Na skróconej karcie **Filtrowanie danych** można zdefiniować dane podstawowe raportu. Użytkownicy tego raportu będą widzieć wartości w raporcie po przetworzeniu danych źródłowych.

| Pole                                                             | opis |
|-------------------------------------------------------------------|-------------|
| Księga rachunku kosztów                                            | **Księga rachunku kosztów**, na której bazuje raport. Wartość jest ustalana na podstawie pola **Jednostka kontroli kosztów**. |
| Jednostka kontroli kosztów                                                 | Wybrana wartość decyduje o księgi rachunku kosztów i obiektach kosztów, na których będzie oparty ten raport. |
| Hierarchia wymiarów statystycznych, Hierarchia wymiarów składników kosztów | Rekord konfiguracji obszaru roboczego **Kontrola kosztów** może przekazywać wartości niepieniężne lub pieniężne, ale nie w tym samym układzie. Wybierz wartość w polu **Hierarchia wymiarów składników kosztów**, aby przekazywać wartości pieniężne. Wybierz wartość w polu **Hierarchia wymiarów statystycznych**, aby przekazywać wartości niepieniężne. Wybrany rekord hierarchii wymiarów określa strukturę poziomów raportowania i agregacji.<blockquote>[!NOTE]<br>Aby wyświetlić wartości niepieniężne i pieniężne obok siebie, można wyeksportować dane do programu Microsoft Excel dla pakietu zawartości usługi Microsoft Power BI.</blockquote> |
| Hierarchia wymiarów obiektów kosztów                                   | Wybierz hierarchię wymiaru obiektu kosztów pasującą do definiowanego celu sprawozdawczości. |
| Pierwotna wersja budżetu                                           | Wybierz identyfikator wersji budżetu pełniącego rolę pierwotnego budżetu w kontekście tego raportu. |
| Skorygowana wersja budżetu                                            | Wybierz identyfikator wersji budżetu pełniącego rolę skorygowanego budżetu w kontekście tego raportu. |

### <a name="assign-calculation-records"></a>Przypisz rekordy obliczeń

Aparat obliczania kosztów ogólnych wykonuje kilka kroków obliczeniowych na danych źródłowych. Np. oblicza klasyfikację zachowania kosztów, dystrybucję kosztów i alokację kosztów. Dla tego samego okresu obrachunkowego można wykonać kilka obliczeń kosztów ogólnych, jeśli na przykład zostanie wykryte brakujące źródło danych lub wystąpi konieczność aktualizacji reguł. Każde obliczenie kosztów ogólnych jest zapisywane z unikatowym identyfikatorem. Księgowy kosztów może wybrać konkretny identyfikator obliczania kosztów ogólnych. Użytkownicy raportów, tacy jak menedżerowie, będą widzieć wyniki obliczania kosztów ogólnych w obszarze roboczym **Kontrola kosztów**.

| Pole                  | opis |
|------------------------|-------------|
| Kalendarzowy okres obrachunkowy | Wybierz okres kalendarza obrachunkowego, do którego ma zostać przypisany identyfikator obliczania kosztów ogólnych.<blockquote>[!NOTE]<br>Okresy obrachunkowe wymienione w tym polu pochodzą z kalendarza obrachunkowego skojarzonego z księgą rachunku kosztów.</blockquote> |
| Wersja rzeczywista         | Wybierz odpowiedni identyfikator obliczania kosztów ogólnych. |
| Wersja budżetu         | Wybierz odpowiedni identyfikator obliczania kosztów ogólnych. |
| Skorygowana wersja budżetu | Wybierz odpowiedni identyfikator obliczania kosztów ogólnych. |

### <a name="fiscal-periods-per-column"></a>Okresy obrachunkowe na kolumnę

Na skróconej karcie **Okresy obrachunkowe na kolumnę** księgowy kosztów decyduje, który okres obrachunkowy powinien być wyświetlany w układzie raportu.

Wartości w wybranych kolumnach zostaną pomnożone przez wybrane wartości na skróconej karcie **Okresy obrachunkowe na kolumnę**.

| Pole                | opis |
|----------------------|-------------|
| Bieżący okres       | Jest wyświetlane saldo bieżącego okresu obrachunkowego.<blockquote>[!NOTE]<br>Domyślnie bieżący okres zależy od daty sesji. W obszarze roboczym **Kontrola kosztów** można wybrać konkretny okres obrachunkowy. Wtedy wybrana wartość reprezentuje bieżący okres.</blockquote> |
| Poprzedni okres      | Jest wyświetlane saldo poprzedniego okresu obrachunkowego. Stosowany jest poniższy wzór:<br>Bieżący okres obrachunkowy – 1<blockquote>[!NOTE]<br>Domyślnie poprzedni okres jest ustalany na podstawie daty sesji. W obszarze roboczym **Kontrola kosztów** można wybrać konkretny okres obrachunkowy jako bieżący okres. Wtedy wartość w polu **Poprzedni okres** zostanie odpowiednio przeliczona.</blockquote> |
| Od początku roku do chwili obecnej         | Jest wyświetlana wartość od początku roku. Stosowany jest poniższy wzór:<br>YearToDate (bieżący okres obrachunkowy)<blockquote>[!NOTE]<br>Domyślnie bieżący okres zależy od daty sesji. W obszarze roboczym **Kontrola kosztów** można wybrać konkretny okres obrachunkowy. Wtedy wybrana wartość reprezentuje bieżący okres, a wartość **Od początku roku do chwili obecnej** zostanie odpowiednio zaktualizowana.</blockquote> |
| Średnia od początku roku do chwili obecnej | Jest wyświetlana średnia wartość od początku roku. Stosowany jest poniższy wzór:<br>(YearToDate [bieżący okres obrachunkowy]) / (Count [bieżący okres obrachunkowy])<p><strong>Przykład</strong></p><ul><li>**Element członkowski wymiaru statystycznego:** Pracownicy etatowi zatrudnieni w pełnym wymiarze czasu</li><li>**Bieżąca data:** 21-3-2017</li><li>**Okres:** Okres obrachunkowy 1, Okres obrachunkowy 2, Okres obrachunkowy 3</li><li>**Wartość:** 10, 10, 12</li></ul>W tym przypadku **Średnia od początku roku do chwili obecnej** = (10 + 10 + 12) ÷ 3 = 10,67<p>Wartość **Średnia od początku roku do chwili obecnej** można obliczyć dla elementów członkowskich wymiaru składnika kosztu i elementów członkowskich wymiaru statystycznego.</p><blockquote>[!NOTE]<br>Domyślnie bieżący okres zależy od daty sesji. W obszarze roboczym **Kontrola kosztów** można wybrać konkretny okres obrachunkowy. Wtedy wybrana wartość reprezentuje bieżący okres, a wartość **Od początku roku do chwili obecnej** i **Średnia od początku roku do chwili obecnej** zostaną odpowiednio zaktualizowane.</blockquote> |

### <a name="columns-to-display-for-costs"></a>Kolumny do wyświetlenia dla kosztów

Na skróconej karcie **Kolumny do wyświetlenia dla kosztów** księgowy kosztów decyduje, które kolumny powinien zawierać układ raportu. Istnieją trzy kategorie: Koszt stały, Koszt zmienny i Koszt niesklasyfikowany.

| Pole                 | opis |
|-----------------------|-------------|
| Koszt stały            | Kolumna tego typu pokazuje koszty stałe w oparciu o wybrany identyfikator obliczania kosztów ogólnych.<blockquote>[!NOTE]<br>Kolumna tego typu będzie pokazywała saldo tylko w przypadku, gdy wybrano identyfikator obliczania kosztów ogólnych dla okresu obrachunkowego.</blockquote> |
| Koszt zmienny         | Kolumna tego typu pokazuje koszty zmienne w oparciu o wybrany identyfikator obliczania kosztów ogólnych.<blockquote>[!NOTE]<br>Kolumna tego typu będzie pokazywała saldo tylko w przypadku, gdy wybrano identyfikator obliczania kosztów ogólnych dla okresu obrachunkowego.</blockquote> |
| Koszt stały + zmienny | Kolumna tego typu pokazuje koszty stałe i zmienne w oparciu o wybrany identyfikator obliczania kosztów ogólnych.<blockquote>[!NOTE]<br>Kolumna tego typu będzie pokazywała saldo tylko w przypadku, gdy wybrano identyfikator obliczania kosztów ogólnych dla okresu obrachunkowego.</blockquote> |
| Łączny koszt            | Kolumna tego typu pokazuje łączny koszt (nieklasyfikowany, stały i zmienny).<blockquote>[!NOTE]<br>Kolumna tego typu zawsze pokazuje saldo.</blockquote> |
| Koszt niesklasyfikowany     | Kolumna tego typu pokazuje koszt niesklasyfikowany.<blockquote>[!NOTE]<br>Ta kolumna może służyć do sprawdzania, czy wszystkie koszty zostały prawidłowo sklasyfikowane przez aparat obliczania kosztów ogólnych, czy też należy skorygować reguły zachowania kosztów.</blockquote> |

### <a name="columns-to-display-for-budgeted-costs"></a>Kolumny do wyświetlenia dla kosztów budżetowych

Na skróconej karcie **Kolumny do wyświetlenia dla kosztów budżetowych** księgowy kosztów decyduje, które kolumny powinny być wyświetlane dla wybranych wersji budżetu. Osobnych wyborów można dokonać dla budżetów pierwotnego i skorygowanego.

> [!NOTE]
> Poniższe pola zachowują się w taki sam sposób dla budżetów pierwotnego i skorygowanego, dlatego opisano je tylko raz.

| Pole                     | opis |
|---------------------------|-------------|
| Budżet                    | Zostaną wyświetlone salda budżetu dla wybranych kolumn.<blockquote>[!NOTE]<br>Salda będą oparte na wersjach budżetu zaznaczonych na skróconej karcie **Filtrowanie danych**.</blockquote> |
| Odchylenie budżetu           | Obliczenie i wyświetlenie różnicy między wartościami zabudżetowanymi a faktycznymi. Stosowany jest poniższy wzór:<br>Saldo budżetu – rzeczywiste saldo |
| Odchylenie budżetu w %      | Obliczenie i wyświetlenie różnicy procentowej między wartościami zabudżetowanymi a faktycznymi. Stosowany jest poniższy wzór:<br>(Saldo budżetu – rzeczywiste saldo) ÷ saldo budżetu |
| Próg odchylenia w okresie | Ustaw wartość progową dla odchylenia kwoty pieniężnej w bieżącym okresie. Jeśli próg zostanie przekroczony, wiersz zostanie wyróżniony na czerwono w obszarze roboczym **Kontrola kosztów**.<blockquote>[!NOTE]<br>To pole dotyczy tylko składników kosztów reprezentujących rozchody.</blockquote> |
| Próg odchylenia w roku   | Ustaw wartość progową dla odchylenia kwoty pieniężnej w roku. Jeśli próg zostanie przekroczony, wiersz zostanie wyróżniony na czerwono w obszarze roboczym **Kontrola kosztów**. |
| Próg odchylenia (%)      | Ustaw wartość progową dla odchylenia w procentach. Jeśli próg zostanie przekroczony, wiersz zostanie wyróżniony na czerwono w obszarze roboczym **Kontrola kosztów**.<blockquote>[!NOTE]<br>Ten sam próg procentowy stosuje się do bieżącego okresu i roku.</blockquote> |

## <a name="cost-control-workspace"></a>Obszar roboczy kontroli kosztów

Obszar roboczy **Kontrola kosztów** został zaprojektowany jako raport sieci Web. W związku z tym wszystkim menedżerom odpowiedzialnym za obiekt kosztów można udzielić dostępu w sposób opisany w temacie [Definiowanie uprawnień dostępu kontrolerów obiektów kosztów](access-rights-cost-object-controller.md).

Lista raportów dostępnych dla użytkowników, na przykład menedżerów, jest kontrolowana przez ustawienie opcji **Opublikowane** na stronie **Konfiguracje obszaru roboczego Kontrola kosztów**.

![Raport widoczny dla użytkowników w obszarze roboczym Kontrola kosztów](./media/report-cost-control.png)

Menedżer może wybrać okres kalendarza obrachunkowego, który ma być wyświetlany. Data sesji określa domyślny bieżący okres.

Wartości w okresie kalendarza obrachunkowego są określane przez nazwę raportu oraz kalendarz obrachunkowy wybrany dla księgi rachunku kosztów skojarzonej z nazwą raportu na stronie **Konfiguracje obszaru roboczego Kontrola kosztów**.

W hierarchii wymiarów obiektów kosztów użytkownicy mogą wybrać poziom agregacji, na którym powinny być wyświetlane salda. Włączając zabezpieczenia na poziomie dostępu, można kontrolować uprawnienia, tak aby użytkownicy mogli wybierać tylko poziomy hierarchii, do których przyznano im dostęp. Z tego względu będą widzieć tylko zagregowane salda, wobec których otrzymali dostęp.

### <a name="add-or-remove-columns"></a>Dodaj lub usuń kolumny

Użytkownicy mogą dostosowywać kolumny w raporcie do własnych potrzeb.

### <a name="view-details"></a>Wyświetlanie szczegółów

Użytkownicy mogą przechodzić do szczegółowych informacji sald wyświetlanych w obszarze roboczym. Jeśli użytkownik zaznaczy węzeł hierarchii wymiarów składników kosztów, a następnie kliknie przycisk **Wyświetl szczegóły**, w oknie dialogowym **Szczegóły składnika kosztu** zostaną wyświetlone szczegółowe informacje dla węzła.

Siatka przedstawia każdy składnik kosztu skojarzony z węzłem hierarchii wymiarów składników kosztów i jego wartość. Kolumny wyświetlane w siatce odpowiadają ustawieniom obszaru roboczego.

Dwa wykresy pokazują podsumowanie porównania wartości rzeczywistych z zabudżetowanymi oraz odchylenie budżetu z podziałem na okresy.

![Wykresy pokazujące podsumowanie porównania wartości rzeczywistych z zabudżetowanymi oraz odchylenie budżetu z podziałem na okresy](./media/cost-element-details-operations.png)

Użytkownicy mogą kliknąć opcję **Wpisy kosztów** i przejść do szczegółów wpisów.

![Wpisy kosztów](./media/cost-entries.png)

Na przykład czynsz jest rozchodem rozdzielanym między centra kosztów. Użytkownik, który chce poznać źródło czynszu przypisanego do jego centrum kosztów, musi przejść do szczegółów, aby zobacz sposób obliczenia czynszu.

Po kliknięciu opcji **Podstawa alokacji** na stronie **Wpisy kosztów** pojawia się okno dialogowe. Użytkownik może wtedy przypisać podstawę alokacji do reguły i przeglądać odnośne mierniki statystyczne zarejestrowane w okresie.

W poniższym przykładzie podstawa alokacji jest typu **Podstawa alokacji formuły** oraz widać formułę. Wymienione są czynniki definiujące formułę. Ponadto siatki przedstawia obliczenia wykonana dla poszczególnych obiektów kosztów.

![Obliczenia dla obiektów kosztów](./media/cost-entries-allocation-base.png)

Dodatkowe zasoby 

[Definiowanie uprawnień dostępu kontrolerów obiektów kosztów](access-rights-cost-object-controller.md)


