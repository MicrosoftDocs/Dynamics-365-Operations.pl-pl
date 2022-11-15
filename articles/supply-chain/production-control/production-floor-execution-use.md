---
title: Jak pracownicy korzystają z interfejsu wykonania hal produkcyjnych
description: W tym artykule opisano sposób korzystania z interfejsu wykonywania pomieszczeń produkcyjnych z punktu widzenia pracownika.
author: johanhoffmann
ms.date: 01/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 876ee36c75a31ca89a9351d0ee1484e66076b6aa
ms.sourcegitcommit: 4abf9b375fed6885ea11a425c524958fea29c3b9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2022
ms.locfileid: "9748721"
---
# <a name="how-workers-use-the-production-floor-execution-interface"></a>Jak pracownicy korzystają z interfejsu wykonania hal produkcyjnych

[!include [banner](../includes/banner.md)]

Interfejs wykonywania pomieszczeń produkcyjnych jest zoptymalizowany pod kątem interakcji dotykowej. Jego projekt stanowi kontrast wizualny odpowiadający wymaganiom dotyczącym ułatwień dostępu w środowisku produkcyjnym. Oferuje wszystkie te same możliwości funkcjonalne, co urządzenie karty zadań. Pozwala to także na uruchamianie wielu zadań równolegle z listy zadań. (Ta możliwość jest również nazywana *przydzieleniem zadań*) Ponadto na podstawie listy zadań pracownicy mogą otwierać Przewodnik utworzony w przewodniku Microsoft Dynamics 365 Guide. W ten sposób mogą uzyskać instrukcje wizualne w HoloLens.

## <a name="sign-in-to-the-production-floor-execution-interface-as-a-worker"></a>Zaloguj się do interfejsu wykonywania hali produkcyjnej jako pracownik

Zanim pracownicy będą mogli rozpocząć korzystanie z urządzenia, kierownik lub personel techniczny musi je przygotować i otworzyć odpowiednią stronę w systemie Dynamics 365 Supply Chain Management. Aby uzyskać więcej informacji o konfigurowaniu urządzenia, zapoznaj się z tematem [Konfigurowanie urządzenia do uruchamiania interfejsu wykonywania pomieszczeń produkcyjnego](production-floor-execution-setup.md).

Po przygotowaniu urządzenia zostanie na nim wyświetlona strona logowania. Na tej stronie są wyświetlane informacje o stanie zadań dla lokalnej komórki roboczej. Te informacje są aktualizowane okresowo. Na stronie pracownicy są używali identyfikatorów karty identyfikacyjnej do podpisania. Chociaż pracownicy nie muszą mieć konta użytkownika służącego do Supply Chain Management, muszą mieć *zarejestrowane konto pracownika*, które mogą być używane podczas logowania.

![Strona logowania do interfejsu wykonania hali produkcyjnej.](media/pfei-sign-in-page.png "Strona logowania do interfejsu wykonania hali produkcyjnej")

Pozostałe sekcje w tym artykule opisują sposób interakcji pracowników z interfejsem.

## <a name="all-jobs-tab"></a>Karta wszystkie zadania

Na karcie **Wszystkie zadania** znajduje się lista zadań pokazująca wszystkie zadania produkcyjne o stanie *Nierozpoczęte*, *Zatrzymane* lub *Rozpoczęte*. (Tę nazwę karty można dostosowywać i może być inna w przypadku Twojego systemu).

![Karta wszystkie zadania.](media/pfei-all-jobs-tab.png "Karta wszystkie zadania")

Lista zadań ma następujące kolumny: Liczby odpowiadają liczbom na poprzedniej ilustracji.

1. **Kolumna wyboru** — skrajna kolumna z lewej strony używa znaczników wyboru w celu wskazania zadań wybranych przez pracownika. Pracownicy mogą wybierać wiele zadań na liście jednocześnie. Aby wybrać wszystkie zadania z listy, zaznacz znacznik wyboru w nagłówku kolumny. W przypadku wybrania jednego zadania szczegóły dotyczące tego zadania są wyświetlane w dolnej części strony.
1. **Kolumna stanu zadania** — w tej kolumnie są używane symbole wskazujące stan każdego zadania. Zadania bez symbolu w tej kolumnie mają stan *Nierozpoczęty*. Zielony trójkąt wskazuje zadania o stanie *Rozpoczęte*. Dwie żółte linie pionowe wskazują zadania o stanie *Zatrzymane*.
1. **Kolumna wysokiego priorytetu** — w tej kolumnie są używane znaki wykrzyknika w celu wskazania zadań o wysokim priorytecie.
1. **Zamówienia** — w tej kolumnie jest wyświetlany numer zlecenia produkcyjnego dla zadania.
1. **Opis** — w tej kolumnie jest wyświetlany opis operacji, której częścią jest zadanie.
1. **Zażądano** — w tej kolumnie jest wyświetlana ilość, która została zaplanowana do wyprodukowania dla zadania.
1. **Rozpoczęte** — w tej kolumnie jest wyświetlana ilość, która została już rozpoczęta dla zadania.
1. **Zakończono** — w tej kolumnie jest wyświetlana ilość, która została już zakończona dla zadania.
1. **Wyrzucono** — w tej kolumnie jest wyświetlana ilość, która została już wyrzucona dla zadania.
1. **Pozostało** — w tej kolumnie jest wyświetlana ilość pozostała do wypełnienia dla zadania.

## <a name="active-jobs-tab"></a>Karta aktywne zadania

Na kartach **Aktywne zadania** znajduje się lista wszystkich zadań, które już rozpoczął zalogowany pracownik. (Tę nazwę karty można dostosowywać i może być inna w przypadku Twojego systemu).

![Karta aktywne zadania.](media/pfei-active-jobs-tab.png "Karta aktywne zadania")

Lista aktywnych zadań ma następujące kolumny:

- **Kolumna wyboru** — skrajna kolumna z lewej strony używa znaczników wyboru w celu wskazania zadań wybranych przez pracownika. Pracownicy mogą wybierać wiele zadań na liście jednocześnie. Aby wybrać wszystkie zadania z listy, zaznacz znacznik wyboru w nagłówku kolumny. W przypadku wybrania jednego zadania szczegóły dotyczące tego zadania są wyświetlane w dolnej części strony.
- **Zamówienia** — w tej kolumnie jest wyświetlany numer zlecenia produkcyjnego dla zadania.
- **Opis** — w tej kolumnie jest wyświetlany opis operacji, której częścią jest zadanie.
- **Zażądano** — w tej kolumnie jest wyświetlana ilość, która została zaplanowana do wyprodukowania dla zadania.
- **Rozpoczęte** — w tej kolumnie jest wyświetlana ilość, która została już rozpoczęta dla zadania.
- **Zakończono** — w tej kolumnie jest wyświetlana ilość, która została już zakończona dla zadania.
- **Wyrzucono** — w tej kolumnie jest wyświetlana ilość, która została już wyrzucona dla zadania.
- **Pozostało** — w tej kolumnie jest wyświetlana ilość pozostała do wypełnienia dla zadania.

## <a name="my-jobs-tab"></a>Karta moje zadania

Na **karcie Moje zadania** pracownicy mogą łatwo przeglądać wszystkie zadania nieukończone i niezakończone, które są przypisane specjalnie do nich. Jest to przydatne w firmach, w których zadania są czasami lub zawsze przydzielane określonym pracownikom (zasobom ludzkim), a nie innym rodzajom zasobów (takich jak maszyny).

System planowania automatycznie przypisuje każde zadanie produkcyjne do określonego rekordu zasobu, a każdy rekord zasobu ma typ (na przykład maszyna lub człowiek). Po skonfigurowaniu pracownika jako pracownika produkcyjnego można skojarzyć konto pracownika z unikalnym rekordem zasobów ludzkich.

Na **karcie Moje zadania** są wyszczególnione wszystkie nieukończone i niezakończone zadania, które zostały przypisane do rekordu zasobów ludzkich zalogowanego pracownika, o ile którykolwiek pracownik jest zalogowany. Nigdy nie wyświetla zadań, które zostały przypisane do komputera lub innego typu zasobu, nawet jeśli zalogowany pracownik rozpoczął pracę nad tymi zadaniami.

Aby wyświetlić wszystkie zadania, które zostały rozpoczęte przez zalogowanego pracownika, niezależnie od typu zasobu, do których jest przypisane każde zadanie, użyj **karty Aktywne zadania**. Aby wyświetlić wszystkie niezakończone zadania zgodne z konfiguracją lokalnego filtru zadań, niezależnie od pracownika lub stanu rozpoczęcia, **użyj karty Wszystkie zadania**.

![Karta moje zadania.](media/pfei-my-jobs-tab.png "Karta moje zadania")

## <a name="my-machine-tab"></a>Karta Moje urządzenie

Na karcie **Moje urządzenie** pracownicy mogą wybrać składnik majątku, który jest połączony z zasobem urządzenia w obrębie filtru ustawionego na karcie **Wszystkie zadania**. Pracownik może następnie wyświetlić stan i kondycję wybranego składnika majątku, odczytując wartości dla maksymalnie czterech wybranych liczników oraz listy ostatnich żądań konserwacji oraz zarejestrowanych przestojów. Pracownik może także zażądać konserwacji wybranego składnika majątku oraz zarejestrowania i edycji przestoju urządzenia. (Tę nazwę karty można dostosowywać i może być inna w przypadku Twojego systemu).

![Karta Moje urządzenie.](media/pfei-my-machine-tab.png "Karta Moje urządzenie")

Na karcie **Moje urządzenie** są wyświetlane następujące kolumny. Liczby odpowiadają liczbom na poprzedniej ilustracji.

1. **Urządzenie — składnik majątku** — umożliwia wybór składnika majątku do śledzenia. Rozpocznij wpisywanie nazwy, aby wybrać z listy pasujących składników majątku, lub wybierz ikonę szkła powiększającego, aby wybrać z listy wszystkich składników majątku skojarzonych z zasobami w filtrze listy zadań.

    > [!NOTE]
    > Użytkownicy aplikacji Supply Chain Management mogą w razie potrzeby przypisać zasób do każdego składnika majątku, korzystając ze strony **Wszystkie składniki majątku** (na karcie **Środki trwałe** przy użyciu listy rozwijanej **Zasób**). Aby uzyskać więcej informacji, zobacz [Tworzenie składnika majątku](../asset-management/objects/create-an-object.md).

1. **Ustawienia** — wybranie ikony narzędzia pozwala otworzyć okno dialogowe, w którym można wybrać liczniki do wyświetlenia dla wybranego składnika majątku dla urządzenia. Wartości tych liczników są wyświetlane w górnej części karty **Zarządzanie składnikami majątku**. Menu **Ustawienia** (widoczne na poniższym zrzucie ekranu) umożliwia włączenie maksymalnie czterech liczników. Dla każdego licznika, który chcesz włączyć, wybierz licznik przy użyciu pola wyszukiwania u góry kafelka. W polu wyszukiwania są wymienione wszystkie liczniki skojarzone ze składnikiem majątku wybranym u góry strony **Zarządzanie składnikami majątku**. Ustawienie każdego licznika w celu monitorowania wartości **zagregowanej** lub ostatniej wartości **rzeczywistej**. Na przykład, jeśli ustawisz licznik, który śledzi czas pracy komputera w godzinach, należy ustawić go na **Zagregowana**. Jeśli licznik jest ustawiany w celu pomiaru ostatniej zaktualizowanej temperatury lub ciśnienia, należy ustawić dla niego wartość **Rzeczywista**. Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć okienko dialogowe.

    ![Ustawienia karty Moje urządzenie.](media/pfei-my-machine-tab-settings.png "Ustawienia karty Moje urządzenie")

1. **Zażądaj konserwacji** — ten przycisk należy wybrać, aby otworzyć okno dialogowe, w którym można utworzyć żądanie konserwacji. Możesz podać opis i uwagę. Żądanie zostanie przesłane do użytkownika aplikacji Supply Chain Management, który będzie mógł przekonwertować żądanie konserwacji na zlecenie pracy dotyczące konserwacji.
1. **Zarejestruj przestój** — ten przycisk należy wybrać, aby otworzyć okno dialogowe, w którym można zarejestrować przestój urządzenia. Możesz wybrać kod przyczyny i wprowadzić okres przestoju w postaci zakresu dat/godzin. Rejestracja przestoju urządzania jest używana do obliczenia wydajności składnika majątku dla urządzenia.
1. **Wyświetl lub edytuj** — ten przycisk należy wybrać, aby otworzyć okno dialogowe, w którym można edytować lub wyświetlać istniejące rekordy przestoju.

## <a name="starting-and-completing-production-jobs"></a>Rozpoczynanie i kończenie zadań produkcyjnych

Pracownicy rozpoczynają zadanie produkcji, zaznaczając zadanie na karcie **Wszystkie zadania**, a następnie wybierając przycisk **Rozpocznij zadanie**, aby otworzyć okno dialogowe **Rozpoczęcie zadania**.

![Okno dialogowe Rozpocznij zadanie.](media/pfei-start-job-dialog.png "Okno dialogowe Rozpocznij zadanie")

Pracownicy używają okna dialogowego **Rozpoczęcie zadania** w celu potwierdzenia ilości produkcji, a następnie uruchomienia zadania. Pracownicy mogą korygować ilość, wybierając pole **Ilość**, a następnie używając wyświetlonej klawiatury numerycznej. Następnie pracownikom wybierz przycisk **Rozpocznij**, aby rozpocząć pracę nad zadaniem. Okno dialogowe **Rozpoczęcie zadania** jest zamknięte, a zadanie jest dodawane do karty **Aktywne zadania**.

Pracownicy mogą uruchamiać zadanie o dowolnym stanie. Jeśli pracownik uruchamia zadanie o stanie *Nierozpoczęte*, w polu **Ilość** w oknie dialogowym **Rozpoczęcie zadania** jest początkowo wyświetlana pełna ilość. Gdy pracownik rozpoczyna zadanie, które ma status *Rozpoczęte* lub *Zatrzymane*, pole **Ilość** początkowo pokazuje pozostałą ilość.

## <a name="reporting-good-quantities"></a>Raportowanie dobrych ilości

Gdy pracownik ukończy lub częściowo wykonuje zadanie, może zgłosić dobre ilości wyprodukowane przez zaznaczenie zadania na karcie **Aktywne zadania**, a następnie wybrać **Postęp raportowania**. Następnie w oknie dialogowym **Postęp raportowania** pracownik wprowadza ilość dobrych za pomocą klawiatury numerycznej. Domyślnie ilość jest pusta. Po wprowadzeniu ilości pracownik może zaktualizować stan zadania jako *W toku*, *Zatrzymany* lub *Ukończony*.

![Okno dialogowe Postęp raportu.](media/pfei-report-progress-dialog.png "Okno dialogowe Postęp raportu")

## <a name="reporting-good-quantities-on-batch-orders-that-have-co-products-and-by-products"></a>Raportowanie dobrych ilości w zamówieniach partii, które mają produkty towarzyszące i uboczne

Pracownicy mogą raportować postęp w realizacji zamówień partii za pomocą interfejsu wykonywania hali produkcyjnej. Raportowanie to obejmuje raportowanie produktów towarzyszących i ubocznych.

Niektórzy producenci, szczególnie w przemyśle procesowym, używają zamówień partii do zarządzania procesami produkcji. Zamówienia partii są tworzone na podstawie formuł i można je zdefiniować w taki sposób, aby w ich wyniku powstawały produkty towarzyszące i uboczne. W przypadku zgłoszonych informacji zwrotnych o tych zamówieniach partii ilość produkcji musi zostać zarejestrowana w produkcie typu formuła, a także w produktach towarzyszących i ubocznych.

Gdy pracownik zakończy lub częściowo zakończy zadanie w zamówieniu partii, może zgłaszać ilości towarów dobrych lub odpadków dla każdego produktu zdefiniowanego jako produkt wyjściowy dla zamówienia. Produkty zdefiniowane jako produkty wyjściowe w zamówieniu partii mogą mieć typ *Formuła*, *Produkt towarzyszący* lub *Produkt uboczny*.

Aby zgłosić dobre ilości produktów, pracownik wybiera zadanie na karcie **Aktywne zadania**, a następnie wybiera opcję **Postęp raportu**.

Następnie w oknie dialogowym **Postęp raportu** pracownik może wybrać spośród produktów, które są zdefiniowane jako produkty wyjściowe dla zamówienia partii, które będą raportować. Pracownik może wybrać jeden lub wiele produktów na liście, a następnie wybrać opcję **Postęp raportu**. W przypadku każdego produktu ilość jest domyślnie pusta, a pracownik może wprowadzić ilość za pomocą klawiatury numerycznej. Pracownik może używać przycisków **Poprzedni** i **Następny**, aby przechodzić między wybranymi produktami. Po wprowadzeniu ilości dla każdego produktu pracownik może zaktualizować stan zadania jako *W toku*, *Zatrzymane* lub *Zakończone*.

![Raportowanie produktów towarzyszących i produktów ubocznych.](media/report-co-by-products.png "Raportowanie produktów towarzyszących i produktów ubocznych")

### <a name="reporting-on-batch-orders-for-planning-items"></a>Raportowanie zamówień partii dotyczących pozycji planowania

Pracownik, który ukończy zadanie w zamówieniu partii dotyczącej pozycji planowania, będzie raportować ilości tylko w odniesieniu do produktów towarzyszących i ubocznych, ponieważ pozycje planowania nie zawierają pozycji typu *Formuła*.

### <a name="reporting-co-product-variation"></a>Raportowanie odchylenia produktu towarzyszącego

Jeśli zamówienie partii jest tworzone na podstawie wersji formuły, w której opcja **Warianty produktów towarzyszących** ma wartość *Tak*, pracownik może składać raporty o produktach towarzyszących, które nie są częścią definicji tych zamówień partii. Ta funkcja jest używana w scenariuszach, w których w procesie produkcji może wystąpić nieoczekiwany produktu wynikowy.

W takim przypadku pracownik może określić produkt towarzyszący w raporcie, zaznaczając w oknie dialogowym postępu raportu **Warianty produktów towarzyszących**. Pracownik może następnie wybrać spośród wszystkich zwolnionych produktów, które są zdefiniowane jako produkty towarzyszące.

### <a name="reporting-catch-weight-items"></a>Zgłaszanie pozycji wagi połowu

Pracownicy mogą używać interfejsu wykonywania na hali produkcyjnej do raportowania postępu w zamówieniach partii, które są tworzone dla pozycji wagi połowu. Zamówienia wsadowe są tworzone na podstawie formuł, które można zdefiniować w taki sposób, aby pozycje wagi połowu były pozycjami formuły, produktami towarzyszącymi i produktami ubocznymi. Formułę można także zdefiniować tak, aby zawierała wiersze formuły dotyczące składników, które zostały określone dla wagi catch. Pozycje w ilości catch używają dwóch jednostek miary do śledzenia zapasów: ilości catch i ilości magazynowej. Na przykład w branży spożywczej mięso pudełek można zdefiniować jako towar w ilości catch, gdzie ilość catch jest używana do śledzenia liczby pudełek, a ilość magazynowa jest używana do śledzenia wagi pudełek.

## <a name="reporting-scrap"></a>Raportowanie odpadków

Gdy pracownik ukończy lub częściowo wykonuje zadanie, może zgłosić odpadki przez zaznaczenie zadania na karcie **Aktywne zadania**, a następnie wybrać **Zgłoś odpadki**. Następnie w oknie dialogowym **Zgłoś odpadki** pracownik wprowadza ilość odpadków za pomocą klawiatury numerycznej. Pracownik również wybiera przyczynę (*Brak*, *Maszyna*, *Operator* lub *Materiały*).

![Okno dialogowe Zgłoś odpadki.](media/pfei-report-scrap-dialog.png "Okno dialogowe Zgłoś odpadki")

## <a name="adjust-material-consumption-and-make-material-reservations"></a>Dostosuj zużycie materiałów i dokonaj rezerwacji materiałów

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Pracownicy mogą dostosować zużycie materiałów do każdego zadania produkcyjnego. Ta funkcjonalność jest używana w scenariuszach, w których rzeczywista ilość materiałów zużytych przez zadanie produkcyjne była większa lub mniejsza od ilości planowanej. Dlatego też musi on być korygowany, aby utrzymać aktualny poziom zapasów.

Pracownicy mogą również dokonywać zastrzeżeń dotyczących numerów partii i serii materiałów. Ta funkcjonalność jest wykorzystywana w scenariuszach, w których pracownik musi ręcznie określić, które numery partii lub serii materiału zostały zużyte, aby spełnić wymagania dotyczące identyfikowalności materiału.

Pracownicy mogą określać ilość do skorygowania, wybierając pozycję **Korygowanie materiału**. Ten przycisk jest dostępny w następujących miejscach:

- W oknie dialogowym **Zgłoś odpadki**
- Okno dialogowe **Raport postępów**
- Na pasku narzędzi po prawej stronie

### <a name="adjust-material-consumption-from-the-report-scrap-and-report-progress-dialog-boxes"></a>Dostosuj zużycie materiału w oknach dialogowych Raport odpadów i Raport postępów

Po wprowadzeniu przez pracownika ilości do raportowania w oknie dialogowym **Raport postępów** lub **Raport odpadów** dostępny staje się przycisk **Dopasuj materiał**. Gdy użytkownik wybierze ten przycisk, zostanie wyświetlone okno dialogowe **Korygowanie materiału**. To okno dialogowe zawiera listę pozycji, które są planowane do zużycia, gdy zgłaszana jest ilość dobra lub złomowana dla zadania.

Lista w oknie dialogowym pokazuje następujące informacje:

- **Numer produktu** – wzorzec produktu i wariant produktu.
- **Nazwa produktu** – Nazwa produktu.
- **Propozycja** – szacowana ilość materiału, która zostanie zużyta w momencie zgłoszonych postępów lub odpadków dla określonej ilości zadania.
- **Zużycie** – rzeczywista ilość materiału, która zostanie zużyta w momencie zgłoszonych postępów lub odpadków dla określonej ilości zadania.
- **Rezerwacja** – ilość materiału fizycznie zarezerwowana w magazynie.
- **Jednostka** – jednostka listy składowej (BOM).

Po prawej stronie okna dialogowego znajdują się następujące informacje:

- **Numer produktu** – wzorzec produktu i wariant produktu.
- **Szacowane** – ilość, która ma zostać zużyta.
- **Rozpoczęte** – ilość rozpoczęta dla zadania produkcyjnego.
- **Pozostała ilość** – z oszacowanej ilości pozostała ilość, która jeszcze nie została zużyta.
- **Ilość wydana** – ilość, która nie została jeszcze zużyta.

Można wykonać następujące czynności:

- Pracownicy mogą określać ilość do skorygowania, wybierając pozycję **Korygowanie zużycia**. Po zatwierdzeniu ilości, ilość w kolumnie **Zużycie** zostaje zaktualizowana o dostosowaną ilość.
- Gdy pracownik wybierze opcję **Korygowanie materiału**, zostanie utworzony arkusz listy pobrania do produkcji. Arkusz zawiera te same towary i ilości co lista **Korygowanie materiałów**.
- Kiedy pracownik dostosowuje ilość w oknie dialogowym **Dopasuj materiał**, pole **Propozycja** w odpowiedniej linii dziennika jest aktualizowane o tę samą ilość. Jeśli pracownik wybierze opcję **Anuluj** w oknie dialogowym **Korygowanie materiału**, lista pobrania zostanie usunięta.
- Jeśli pracownik wybierze przycisk **OK**, lista pobrania nie zostanie usunięta. Zostanie on zaksięgowany po raporcie zadania w oknie dialogowym **Raport odpadów** lub **Raport postępów**.
- Jeśli pracownik wybierze opcję **Anuluj** w oknie dialogowym **Raport postępów** lub **Raport odpadów**, lista pobrania zostanie usunięta.

### <a name="adjust-material-from-the-primary-or-secondary-toolbar"></a>Dostosuj materiał z głównego lub dodatkowego paska narzędzi

Przycisk **Korygowanie materiału** można skonfigurować w taki sposób, by pojawiał się na głównym lub dodatkowym pasku narzędzi. (Więcej informacji znajdziesz w [Zaprojektuj interfejs wykonawczy hali produkcyjnej](production-floor-execution-tabs.md).) Pracownik może wybrać **Dostosuj materiał** dla zadania produkcyjnego, które jest w toku. W tym przypadku zostanie wyświetlone okno dialogowe **Korekta materiału**, w którym pracownik może dokonać żądanych korekt. Gdy okno dialogowe zostanie otwarte, dla zlecenia produkcyjnego zostanie utworzona produkcyjna lista pobrań, która zawiera wiersze dla dostosowanych ilości. Jeśli pracownik wybierze opcję **Księguj teraz**, korekta zostanie potwierdzona i zostanie zaksięgowana lista pobrania. Jeśli pracownik wybierze opcję **Anuluj**, lista pobrań zostaje usunięta i nie dokonuje się żadnej korekty.

### <a name="adjust-material-consumption-for-catch-weight-items"></a>Dostosuj zużycie materiału dla elementów wagi połowu

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Pracownicy mogą dostosowywać zużycie materiału dla elementów wagi połowu. Ta funkcja jest używana w scenariuszach, w których rzeczywista ilość materiału wagi połowu, która została zużyta przez zadanie produkcyjne, była większa lub mniejsza niż ilość planowana. Dlatego też musi on być korygowany, aby utrzymać aktualny poziom zapasów. Gdy pracownik koryguje zużycie elementu wagi połowu, może dostosować zarówno ilość wagi połowu, jak i ilość zapasów. Na przykład, jeśli w zadaniu produkcyjnym planuje się spożycie pięciu pudełek o szacunkowej wadze 2 kilogramów na pudło, pracownik może dostosować zarówno liczbę pudełek do spożycia, jak i wagę pudeł. System zweryfikuje, czy określona waga pudełek mieści się w określonym minimalnym i maksymalnym progu, który zdefiniowano na zwolnionym produkcie.

### <a name="reserve-materials"></a>Rezerwuj materiały

W oknie dialogowym **Koryguj materiał** pracownik może dokonać i dostosować rezerwację materiału, wybierając **Zarezerwuj materiał**. W oknie dialogowym **Rezerwacja materiału** wyświetlane są fizycznie dostępne zapasy towaru dla poszczególnych wymiarów przechowywania i śledzenia.

Jeśli materiał jest włączony w procesy magazynowe (WMS), lista pokazuje tylko fizycznie dostępne zapasy dla miejsca wejścia do produkcji dla danego materiału. Miejsce wejścia do produkcji jest zdefiniowane w zasobie, w którym zaplanowane jest zadanie produkcyjne. Jeśli numer pozycji jest kontrolowany przez numer partii lub numer seryjny, pokaże się pełna lista fizycznie dostępnych numerów partii i numerów seryjnych. Aby określić ilość do rezerwacji, pracownik może wybrać opcję **Rezerwuj materiał**. Aby usunąć istniejącą rezerwację, pracownik może wybrać opcję **Usuń rezerwację**.

Aby uzyskać więcej informacji dotyczących konfigurowania lokalizacji wejściowej produkcji, zobacz następujący wpis w blogu: [Konfigurowanie lokalizacji wejściowej produkcji](/archive/blogs/axmfg/deliver-picked-materials-to-the-locations-where-the-materials-are-consumed-by-operations-in-production).

> [!NOTE]
> Rezerwacje przez pracownika w oknie dialogowym **Rezerwacja materiałów** pozostają, gdy pracownik wybierze opcję **Anuluj** w oknie dialogowym **Raport postępów** lub **Raport odpadów**.
>
> Nie można skorygować rezerwacji pozycji w kg.

## <a name="completing-a-job-and-starting-a-new-job"></a>Kończenie zadania i rozpoczynanie nowego zadania

Zazwyczaj pracownicy wypełniają zadanie, wybierając jedno lub więcej zadań bieżących na karcie **Aktywne zadania**, a następnie wybierając opcję **Raportuj postęp**. Następnie wprowadź ilość wyprodukowaną (ilość dobrych) i określ stan na *Zakończony*. Jeśli zaznaczono więcej niż jedno zadanie, do przechodzenia między nimi są używane przyciski **Poprzedni** i **Następny**. Aby rozpocząć nowe zadanie, pracownik wybiera go na karcie **Wszystkie zadania**, a następnie wybiera **Zadanie rozpoczęcia**.

Pracownik może również uruchomić nowe zadanie, gdy poprzednie zadanie jest otwarte. Ponownie, aby rozpocząć nowe zadanie, pracownik wybiera go na karcie **Wszystkie zadania**, a następnie wybiera **Zadanie rozpoczęcia**. Jednak w tym przypadku okno dialogowe **Rozpoczęcie zadania** informuje pracownika, że aktualnie pracuje nad zadaniem, i dlatego musi je zatrzymać lub zakończyć przed rozpoczęciem nowego zadania.

## <a name="working-on-multiple-jobs-in-parallel"></a>Praca nad wieloma zadaniami równolegle

Jeden pracownik może jednocześnie pracować z wieloma zadaniami (równolegle). W takim przypadku zbieranie zadań, nad którymi pracuje pracownik, jest nazywane *pakietem zadań*. Pracownik może dodawać nowe zadania do pakietu lub wykonywać jedno lub więcej zadań w pakiecie. Poniższe dwa scenariusze pokazują, w jaki sposób pracownik może pracować równolegle z zadaniami.

### <a name="scenario-1-a-worker-who-has-no-active-jobs-wants-to-start-two-jobs-and-work-on-them-in-parallel"></a>Scenariusz 1: pracownik, który nie ma aktywnych zadań, chce rozpocząć dwa zadania i pracować równolegle

Pracownik wybiera dwa zadania na karcie **Wszystkie zadania**, a następnie wybiera **Zadanie rozpoczęcia**. W oknie dialogowym **Rozpoczęcie zadania** wyświetlane są zarówno wybrane zadania, jak i pracownik, który może zmienić ilość na początkową dla każdego zadania. Następnie pracownik potwierdzi to okno dialogowe i może uruchomić oba zadania.

### <a name="scenario-2-a-worker-who-has-two-active-jobs-that-are-in-progress-wants-to-start-a-third-job-and-work-on-it-in-parallel-with-the-other-two"></a>Scenariusz 2: pracownik, który ma dwa aktywne zadania będące w toku, chce rozpocząć trzecie zadanie i pracować nad nim równolegle z dwoma innymi

Pracownik wybiera trzecie zadanie na karcie **Wszystkie zadania**, a następnie wybiera **Pakiet**. W oknie dialogowym **Pakiet** pracownik może skorygować ilość do rozpoczęcia. Następnie pracownik zatwierdza okno dialogowe, wybierając opcję **Pakiet**.

## <a name="working-on-indirect-activities"></a>Praca przy działaniach pośrednich

Działania pośrednie to działania, które nie są bezpośrednio związane ze zleceniem produkcyjnym. Działania pośrednie można definiować elastycznie, jak to opisano w temacie [Ustawianie działań pośrednich dla modułu czas i frekwencja](/dynamicsax-2012/appuser-itpro/set-up-indirect-activities-for-time-and-attendance).

Na przykład Shannon, pracownica hali w firmie Contoso, chce uczestniczyć w spotkaniu firmy, a spotkania są traktowane jako działania pośrednie. Ma zastosowanie jedno z następujących dwóch scenariuszy:

- **Shannon pracuje z co najmniej jednym aktywnym zadaniem.** Shannon wybiera **Działanie**, identyfikuje działanie (spotkanie) i potwierdza jego wybór. Komunikat informujący, że posiada zadania, które są w toku. Na podstawie wiadomości Shannon może wybrać opcję ukończenia lub zatrzymania zadań, nad którymi pracuje, zanim zostaną one przechodzące na spotkanie.
- **Shannon nie ma żadnych aktywnych zadań.** Shannon wybiera **Działanie**, identyfikuje działanie (spotkanie) i potwierdza jego wybór. Jest obecnie zarejestrowana jako przebywająca na spotkaniu.

W obu przypadkach, po potwierdzeniu przez Shannon wyboru, przechodzi do strony logowania lub strony, która będzie czekać, aż potwierdzi, że wróciła ze swojej pośredniej działalności. Wyświetlana strona zależy od konfiguracji interfejsu wykonywania pomieszczeń produkcyjnych. (Aby uzyskać więcej informacji, zobacz [Konfigurowanie interfejsu wykonania hal produkcyjnych](production-floor-execution-configure.md).)

## <a name="registering-breaks"></a>Rejestrowanie przerw

Pracownicy mogą rejestrować przerwy. Przerwy można definiować elastycznie, zgodnie z opisem w [Płaca oparta na rejestracjach](pay-based-on-registrations.md).

Pracownik rejestruje przerwę, wybierając opcję **Przerwa**, a następnie wybierając kartę, która reprezentuje typ przerwy (np. obiad). Gdy pracownik potwierdzi wybór, na urządzeniu zostanie wyświetlona strona logowania lub strona, która będzie czekać, aż pracownik potwierdzi, że wrócił z przerwy. Wyświetlana strona zależy od konfiguracji interfejsu wykonywania pomieszczeń produkcyjnych. (Aby uzyskać więcej informacji, zobacz [Konfigurowanie interfejsu wykonania hal produkcyjnych](production-floor-execution-configure.md).)

## <a name="view-the-my-day-dialog"></a>Wyświetl okno dialogowe „Mój dzień”

Okno dialogowe **Mój dzień** umożliwia pracownikom przegląd ich rejestracji i sald. Dialog jest podzielony na trzy następujące części:

- Sekcja główna zawiera listę rejestracji, których aktualny pracownik dokonał w wybranym dniu. Otwiera się on, pokazując rejestracje na bieżący dzień, a także umożliwia wybór daty, dzięki czemu pracownik może zobaczyć inne dni.
- Sekcja **Ostatnie obliczone saldo dzienne** pokazuje aktualne salda pracownika dotyczące płatnego czasu pracy, płatnych nadgodzin, nieobecności i płatnej nieobecności. Wartości te są oparte na rejestracjach, które zostały obliczone podczas procesu zatwierdzania.
- Sekcja **Balanse** zawiera przegląd sald w określonym okresie dla wybranych kategorii rejestracji (takich jak urlopy, czas standardowy i nadgodziny). Salda te opierają się na sposobie, w jaki ustawia się salda statystyczne w module **Czas pracy i obecność**. Aby uzyskać więcej informacji o tym, jak to ustawić, zobacz [Pokaż salda urlopów w interfejsie wykonawczym hali produkcyjnej](production-floor-execution-payroll-stats.md).

Administratorzy mogą dodać tę funkcję do interfejsu, umieszczając przycisk **Mój dzień** na pasku narzędzi dla każdej odpowiedniej zakładki, jak opisano w [Projektowanie interfejsu wykonawczego hali produkcyjnej](production-floor-execution-tabs.md).

## <a name="working-in-teams"></a>Praca w zespołach

Kiedy kilku pracowników jest przydzielonych do tego samego zadania produkcyjnego, mogą oni tworzyć zespół. Drużyna może wyznaczyć jednego pracownika jako pilota. Pozostali pracownicy automatycznie stają się asystentami tego pilota. W powstałej w ten sposób drużynie tylko pilot musi zarejestrować status pracy. Ewidencja czasu pracy dotyczy wszystkich członków zespołu.

### <a name="prerequisites"></a>Wymagania wstępne

Aby móc korzystać z zespołów, administrator musi włączyć akcję **Asysstent** dla głównego paska narzędzi w zakładce **Wszystkie zadania** w interfejsie wykonawczym hali produkcyjnej. Aby uzyskać więcej informacji, zobacz [Projektowanie interfejsu wykonania hal produkcyjnych](production-floor-execution-tabs.md).

### <a name="form-a-new-team-that-has-a-pilot-and-an-assistant"></a>Utwórz nową drużynę, która będzie miała pilota i asystenta

Pracownik może zarejestrować się jako asystent, wybierając **Asystenta** w zakładce **Wszystkie zadania**. Następnie w wyświetlonym oknie dialogowym **Wybierz pracownika do asystowania** pracownik może wybrać pilota z listy pracowników, którzy aktywnie pracują nad danym zadaniem. Gdy pracownik potwierdzi swój wybór, zostaje asystentem wybranego pracownika, który staje się pilotem nowego zespołu.

### <a name="assign-a-new-pilot-to-an-existing-team"></a>Przydziel nowego pilota do istniejącego zespołu

Kiedy drużyna chce wybrać nowego pilota, obecny pilot musi wyznaczyć innego pracownika w zespole na nowego pilota. Aby wyznaczyć nowego pilota, obecny pilot wybiera **Asystenta** w zakładce **Wszystkie zadania**. Następnie, w wyświetlonym oknie dialogowym **Zmień pilota**, pilot może wybrać nowego pilota z listy pracowników, którzy już są w zespole. Gdy aktualny pilot potwierdzi swój wybór, zostaje on całkowicie usunięty z drużyny. Mogą jednak powrócić do zespołu, gdy będą tego potrzebować.

### <a name="assistant-clocks-out"></a>Asystent kończy pracę

Kiedy pracownik, który pracuje jako asystent, odchodzi z zespołu. Jeśli opcje **Stałe zespoły** i **Restart po włączeniu** są ustawione na *Tak*, pracownik, który się wylogował, automatycznie dołączy do zespołu przy następnym włączeniu. Opcje te możesz znaleźć w zakładce **Ogólne** na stronie **Parametry czasu pracy**.

## <a name="opening-instructions"></a>Otwieranie instrukcji

Pracownicy mogą otwierać dokument dołączony do stanowiska, wybierając odpowiednie **Instrukcje**. Przycisk **Instrukcje** jest dostępny tylko wtedy, gdy dokument jest skojarzony z zadaniem w danych głównych. Na przykład dokument dołączony do produktu na stronie **Zwolnione produkty** w module Supply Chain Management będzie dostępny dla pracowników, którzy będą otwierali się w interfejsie realizacji produkcji.

## <a name="opening-mixed-reality-guides-for-hololens"></a>Otwieranie przewodników rzeczywistości mieszanej dla HoloLens

[Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/) ułatwiają pracownikom udzielanie informacji poprzez dostarczanie wskazówek, które korzystają z rzeczywistości mieszanej. Możesz zdefiniować znormalizowane procesy, w których instrukcje krok po kroku kierują pracowników do potrzebnych im narzędzi i części oraz pokazują, jak używać tych narzędzi w rzeczywistych sytuacjach zawodowych. Poniżej znajduje się omówienie procesu.

1. Za każdym razem, gdy pracownik otwiera listę zadań w interfejsie wykonywania prac produkcyjnych, interfejs wyszukuje wszystkie odpowiednie przewodniki dotyczące wyświetlanych zadań.
1. Pracownik wybiera **Przewodniki**, aby wyświetlić listę poradników.
1. Pracownik wybiera odpowiedni przewodnik z listy.
1. Interfejs realizacji oddziału produkcyjnego pokazuje kod QR dla wybranego przewodnika.
1. Pracownik wprowadza do systemu HoloLens i rzutuje kod QR, aby rozpocząć Przewodnik.
1. Pracownik pracuje z przewodnikiem w celu uzyskania informacji o zadaniu.

Aby uzyskać więcej informacji na temat sposobu tworzenia, przypisywania i używania przewodników dla HoloLens, zapoznaj się z tematem [Zapewnianie przewodników Guides rzeczywistości mieszanej dla pracowników w produkcji](instruction-guides-in-production-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
