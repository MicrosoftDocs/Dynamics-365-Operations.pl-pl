---
title: Możliwości siatki
description: W tym artykule opisano kilka zaawansowanych funkcji formantu siatki. Musisz włączyć nową funkcje siatki, aby można było uzyskać dostęp do tych możliwości.
author: jasongre
ms.date: 08/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 6d14bba13dbf701a8c27c10ac2d318b071092bc1
ms.sourcegitcommit: 77ffeccffff28fbb6ff576864d7abddd412cdab6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/15/2022
ms.locfileid: "9852392"
---
# <a name="grid-capabilities"></a>Możliwości siatki

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Nowa kontrolka siatki zapewnia kilka przydatnych i zaawansowanych funkcji, które mogą być używane w celu zwiększenia wydajności użytkowników, tworzenia bardziej interesujących widoków danych oraz uzyskiwania informacji o szczegółowych danych. Ten artykuł będzie obejmował następujące możliwości: 

- Wyświetlanie obliczonych wartości 
- Pisanie przed systemem
- Ocenianie wyrażeń matematycznych 
- Grupowanie danych tabelarycznych (włączone oddzielnie za pomocą funkcji **Grupowania w module siatki**)
- Zamrażanie kolumn (włączane oddzielnie przy użyciu funkcji **Zamrażanie kolumn w siatkach**)
- Automatyczne dopasowanie szerokości kolumny
- Rozszerzalne kolumny

## <a name="showing-calculated-values"></a>Wyświetlanie obliczonych wartości
W aplikacjach finansowych i operacyjnych użytkownicy mogą wyświetlać obliczoną wartość dla każdej kolumny liczbowej w siatce. Sekcja stopki na dole siatki pokazuje te obliczone wartości.

[![Wyświetlanie obliczonych wartości w siatkach.](./media/grids-aggregation.png)](./media/grids-aggregation.png)

W wersjach wcześniejszych niż 10.0.29 jedyną obsługiwaną wartością obliczoną jest suma. Jednak od wersji 10.0.29, **po włączeniu funkcji agregacji rozszerzonej siatki**, użytkownicy mogą wybrać spośród czterech następujących obliczonych wartości:

- Minimalna
- Maksymalna
- Razem
- Średnia

W jednej kolumnie może być pokazywany tylko jeden typ obliczanej wartości. Jednak każda kolumna w siatce może być skonfigurowana tak, aby zawierała inny typ obliczanej wartości.

### <a name="showing-the-grid-footer"></a>Pokazywanie stopki siatki
W dolnej części każdej siatki tabelarycznej w aplikacjach finansowych i operacyjnych znajduje się obszar stopki. Stopka może zawierać cenne informacje związane z danymi wyświetlanymi w siatce. Oto kilka przykładów takich informacji:

- Liczba zaznaczonych wierszy w tabeli (gdy zaznaczysz więcej niż jeden rekord)
- Obliczone wartości na dole skonfigurowanych kolumn liczbowych (na przykład sumy końcowe)
- Liczby kolumn w zestawie danych 

Ta stopka jest domyślnie ukryta, ale możesz ją włączyć. Aby wyświetlić stopkę siatki, wybierz przycisk **Opcje siatki** w nagłówku siatki i wybierz opcję **Pokazuj stopkę**. Po włączeniu stopki dla określonej siatki to ustawienie będzie przypominane do czasu, aż użytkownik wybierze opcję ukrywania stopki. Aby ukryć stopkę, wybierz opcję **Ukryj stopkę** w menu **Opcje siatki**.

### <a name="specifying-columns-with-calculated-values"></a>Określanie kolumn z obliczonymi wartościami
Obecnie żadne kolumny nie wyświetlają domyślnie obliczonych wartości. Zamiast tego konfiguracja jest uważana za jednorazową czynność, taką jak dostosowywanie szerokości kolumn w siatkach. Po określeniu, że chcesz wyświetlić obliczoną wartość dla kolumny, to ustawienie zostanie zapamiętane przy następnej wizycie na stronie.

Istnieją dwa sposoby skonfigurowania kolumny do wyświetlania obliczonej wartości:

- Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) w kolumnie, dla której chcesz wyświetlić obliczoną wartość. Jeśli funkcja agregacji **rozszerzonej siatki** jest włączona, wybierz **pozycję Wyświetl sumy** kolumn, a następnie wybierz żądaną obliczoną wartość. Jeśli ta funkcja nie jest włączona, wybierz pozycję **Suma w tej kolumnie**. Ta akcja powoduje wystąpienie trzech zdarzeń:

    1. Stopka siatki staje się widoczna. 
    2. Zostaną zapisane preferencje dotyczące wyświetlania obliczonej wartości kolumny. 
    3. Żądane obliczenie jest inicjowane dla kolumny i wszystkich innych kolumn, które wcześniej skonfigurowano do wyświetlania obliczonej wartości. Czas wymagany do wyświetlenia obliczonych wartości zależy od rozmiaru zestawu danych.

- Gdy stopka będzie widoczna, wybierz pozycję **Pokaż sumę** (**lub Wybierz wartość obliczoną**, jeśli jest włączona funkcja **agregacji rozszerzonej siatki**) w obszarze stopki u dołu kolumny, dla której chcesz wyświetlić obliczoną wartość. Jeśli nie ma skonfigurowanych kolumn, ten przycisk będzie dostępny w stopce we wszystkich kolumnach liczbowych.

    Po skonfigurowaniu co najmniej jednej kolumny tak, aby wyświetlała obliczoną wartość, przycisk **Pokaż sumę** (lub **Wybierz obliczoną wartość**) będzie dostępny tylko przy umieszczeniu kursora lub fokusu. Akcja wybrania przycisku po prostu zapisuje preferencje wyświetlania obliczonej wartości w kolumnie, dzięki czemu preferencja zostanie zastosowana podczas przyszłych wizyt na stronie. W stopce ten stan jest wskazywany przez kreskę wyświetlaną w kolumnie. (Jeśli zestaw danych jest wystarczająco mały, obliczona wartość pojawi się natychmiast)

Jeśli popełnisz błąd i nie chcesz już wyświetlać obliczonej wartości w określonej kolumnie, wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) w kolumnie, a następnie wybierz **Ukryj sumę** (lub **Wyświetl sumy kolumn \> Brak** jeśli włączona jest funkcja **Rozszerzone możliwości agregacji sieci**). Możesz również wybrać opcję **Ukryj sumę** (lub **Ukryj obliczoną wartość**) w stopce tej kolumny. Ta preferencja zostanie również zapisana dla przyszłych odwiedzin na stronie. 

### <a name="calculating-aggregate-values"></a>Obliczanie wartości zagregowanych
Gdy przejdź do strony, na której stopka jest widoczna, a kolumny są już skonfigurowane tak, aby były wyświetlane obliczone wartości, te wartości mogą nie być wyświetlane w stopce. Zachowanie zależy od rozmiaru zestawu danych na stronie. Jeśli zestaw danych jest wystarczająco mały, obliczone wartości zostaną wyświetlone automatycznie wraz z liczbą wierszy w zestawie danych. Jeśli w stopce znajdują się myślniki pod skonfigurowanymi kolumnami, zestaw danych jest zbyt duży, aby system mógł natychmiast wyświetlić obliczone wartości. W tym przypadku do obliczenia wartości jest wymagana jawna akcja. Aby obliczyć wartości, należy wybrać przycisk **Oblicz** w stopce. Możesz też wybrać i przytrzymać (lub kliknąć prawym przyciskiem myszy) w kolumnie, dla której chcesz wyświetlić sumę, a następnie wybrać **Łącznie w tej kolumnie** (lub **Wyświetl sumy kolumn** i żądaną obliczoną wartość jeśli włączona jest funkcja **Rozszerzone możliwości agregacji sieci**).

Jeśli wykonanie obliczeń zajmuje dużo czasu, możesz anulować operację w dowolnym momencie, wybierając **Anuluj**. Zestaw danych może być zbyt duży, aby można było obliczyć wartości zagregowane (limit nakładany przez organizację). W takim przypadku użytkownik zostanie poinformowany o większej liczby filtrowanych danych.

> [!NOTE]
> Administratorzy systemu mogą modyfikować limit liczby rekordów dostępnych do obliczania agregatów, dostosowując **Maksymalna liczba rekordów lokalnych dla każdego parametru siatki** na stronie **Opcje wydajności klienta**. Wartość domyślna to 25000 rekordów. Administratorzy powinni zachować ostrożność podczas dostosowywania tej wartości, ponieważ zbyt duża wartość może wyczerpać dostępną pamięć na komputerze użytkownika. Zalecamy, aby wartość nie przekraczała 50 000 rekordów.

Obliczone wartości będą automatycznie aktualizowane podczas aktualizacji, usuwania lub tworzenia wierszy w zestawie danych.

## <a name="typing-ahead-of-the-system"></a>Pisanie przed systemem
W wielu scenariuszach biznesowych możliwość szybkiego wprowadzania danych do systemu jest bardzo ważna. Przed wprowadzeniem nowej kontroli sieci użytkownicy mogli zmieniać dane tylko w bieżącym wierszu. Z tego względu po wytworzeniu zmian w wierszu użytkownicy nie mogli przełączać się do innego wiersza ani tworzyć nowego wiersza, dopóki nie zostaną zweryfikowane zmiany w bieżącym wierszu i (w przypadku tworzenia wiersza) uruchomią wszystkie logikę skojarzoną z tworzeniem nowego wiersza. Aby skrócić czas oczekiwania użytkowników na zakończenie tych operacji i zwiększyć produktywność użytkowników, nowa siatka dostosowuje te działania tak, aby były asynchroniczne. Użytkownicy mogą tworzyć nowe wiersze lub przechodzić do innych wierszy, aby wprowadzać zmiany, podczas gdy oczekujące są walidacje poprzednich wierszy i logika tworzenia wierszy. 

[![Pisanie przed systemem.](./media/gridFastEntry-07-25-2022.gif)](./media/gridFastEntry-07-25-2022.gif)

Aby można było obsłużyć to nowe zachowanie, nowa kolumna dla stanu wiersza została dodana po prawej stronie kolumny wyboru wiersza, gdy siatka jest w trybie edycji. W tej kolumnie jest wskazywany jeden z następujących stanów:

- **Pusty** — Brak obrazu stanu wskazuje, że wiersz został pomyślnie zapisany przez system.
- **Przetwarzanie w toku** — Ten stan wskazuje, że zmiany w wierszu nie zostały jeszcze zapisane przez serwer, ale znajdują się w kolejce zmian, które muszą zostać przetworzone. Przed wykonaniem akcji poza siatką należy poczekać na przetworzenie wszystkich oczekujących zmian. Ponadto tekst w tych wierszach jest pisany kursywą w celu wskazania niezapisanego stanu wierszy. 
- **Nieprawidłowy stan** — Ten stan wskazuje, że podczas przetwarzania wiersza zostało wyzwolone pewne ostrzeżenie lub komunikat, co mogło uniemożliwić systemowi zapisanie zmian w tym wierszu. W starej siatce, jeśli operacja zapisu nie powiodła się, zostaniesz przeniesiony z powrotem do wiersza, aby natychmiast rozwiązać problem. Jednak w nowej siatce zostanie wyświetlone powiadomienie, że napotkano problem z weryfikacją, ale można zdecydować, kiedy mają być naprawione wszystkie problemy występujące w danym wierszu. Gdy wszystko będzie gotowe do rozwiązania problemu, można ręcznie przenieść uwagę z powrotem na wiersz. Alternatywnie można wybrać akcję **Napraw ten problem**. Ta akcja powoduje natychmiastowe przeniesienie uwagi z powrotem do wiersza, którego dotyczy ten błąd, oraz umożliwia wprowadzanie zmian w siatce lub poza nią. Należy zauważyć, że przetwarzanie kolejnych wierszy oczekujących zostało zatrzymane do czasu rozwiązania tego ostrzeżenia o sprawdzeniu poprawności. 
- **Wstrzymano** — Ten stan wskazuje, że przetwarzanie przez serwer zostało wstrzymane, ponieważ weryfikacja wiersza wyzwoliła wyskakujące okno dialogowe, które wymaga wprowadzenia danych przez użytkownika. Ponieważ użytkownik może wprowadzać dane w innym wierszu, wyskakujące okno dialogowe nie jest natychmiast prezentowane użytkownikowi. Zamiast tego zostanie on przedstawiony, gdy użytkownik wybierze opcję wznowienia przetwarzania. Do tego stanu dołączane jest powiadomienie, które informuje użytkownika o sytuacji. Powiadomienie zawiera akcję **Wznawiania przetwarzania**, która będzie wyzwalać wyskakujące okno dialogowe.

### <a name="differences-when-entering-data-ahead-of-the-system"></a>Różnice podczas wprowadzania danych przed systemem
W wprowadzeniu danych przed miejscem przetwarzania systemu można oczekiwać kilku zmian w doświadczeniu w zakresie wprowadzania danych:

- Można zauważyć, że nie ma list rozwijanych, wartości pól nie zostaną zweryfikowane po przejściem do innej kolumny w tym samym wierszu, a kolumny początkowo nie wskazują wartości domyślnych. Działanie to występuje podczas tworzenia lub aktualizowania przed systemem. Jednak po zakończeniu edycji systemu do miejsca, w którym jest aktualnie edytowane, zostanie wznowione standardowe doświadczenie. Jeśli w polu, które zwykle otrzymuje wartość domyślną, zmiany zastępują wartość pola domyślnego, gdy serwer rozpoczyna przetwarzanie wiersza.
- W przypadku tworzenia nowego wiersza przy użyciu **klawisza strzałki w dół** wszystkie kolumny w siatce będą wyświetlane jako edytowalne. Domyślnie fokus jest umieszczany w pierwszej kolumnie w nowym wierszu. Ta kolumna może nie być tą samą kolumną, która otrzymała fokus początkowy w starszej siatce, lub tą samą kolumną, która otrzymuje fokus po wybraniu przycisku **Nowy**. Organizacja może dostosować system i zmienić kolumnę, która otrzymuje fokus początkowy po wybraniu klawisza **strzałki w dół**. Aby uzyskać więcej informacji, zobacz temat [Określanie kolumny, która otrzymuje fokus początkowy podczas tworzenia nowych wierszy przy użyciu sekcji Klawisz strzałki w dół](#developer-specifying-the-column-that-receives-the-initial-focus-when-new-rows-are-created-by-using-the-down-arrow-key). Niezależnie od tego można użyć personalizacji w celu zoptymalizowania każdej siatki pod kątem wprowadzania danych. W szczególności można zmieniać kolejność pól, tak aby pierwsza kolumna stanowiła kolumnę, w której mają się rozpocząć wprowadzanie danych. Można także zmienić kolejność pól na potrzeby wprowadzania danych, aby ograniczyć liczbę zatrzymań kart i ukryć pola, które nie są wymagane do wprowadzania danych w tym określonym widoku.

### <a name="pasting-from-excel"></a>Wklejanie z programu Excel
Użytkownicy zawsze mogli eksportować dane z siatek w aplikacjach finansowych i operacyjnych do programu Microsoft Excel za pomocą mechanizmu **Eksport do programu Excel**. Jednak możliwość wprowadzania danych przed systemem umożliwia nowej siatce obsługę kopiowania tabel z programu Excel i wklejanie ich bezpośrednio do siatek w aplikacjach finansowych i operacyjnych. Komórka siatki, z której jest inicjowana operacja wklejenia określa miejsce, w którym rozpocznie się wklejanie skopiowanej tabeli. Zawartość siatki jest zastępowana zawartością skopiowanej tabeli, z wyjątkiem dwóch przypadków:

- Jeśli liczba kolumn w kopiowanej tabeli przekracza liczbę kolumn pozostających w siatce, rozpoczynając od lokalizacji wklejania, użytkownik zostanie poinformowany, że dodatkowe kolumny zostały zignorowane. 
- Jeśli liczba wierszy w kopiowanej tabeli przekracza liczbę wierszy w siatce, począwszy od lokalizacji wklejania, istniejące komórki zostaną zastąpione przez wklejoną zawartość, a wszystkie dodatkowe wiersze ze skopiowanej tabeli zostaną wstawione jako nowe wiersze u dołu siatki. 

## <a name="evaluating-math-expressions"></a>Ocenianie wyrażeń matematycznych
Jako środek zwiększający produktywność, użytkownicy mogą wprowadzać formuły matematyczne w komórkach liczbowych w siatce. Nie muszą one przeliczać w aplikacji poza systemem. Jeśli na przykład wprowadzisz wartość **=15\*4**, a następnie naciśnij klawisz **Tab**, aby przenieść się z pola, system oszacuje wyrażenie i zapisze wartość **60** dla tego pola.

[![Ocenianie wyrażeń matematycznych.](./media/gridMathExpression-07-25-2022.gif)](./media/gridMathExpression-07-25-2022.gif)

Aby system rozpoznawał wartość jako wyrażenie, należy uruchomić wartość ze znakiem równości (**=**). Więcej informacji na temat obsługiwanych operatorów i składni zawiera sekcja [obsługiwane symbole matematyczne](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

Z wersją 10.0.29 możliwość oceniania wyrażeń matematycznych w formantach liczbowych została rozszerzona i jest również dostępna poza siatką.

## <a name="grouping-tabular-data"></a>Grupowanie danych tabelarycznych
Użytkownicy biznesowi często muszą przeprowadzać analizę danych ad hoc. Chociaż tę analizę można przeprowadzić, eksportując dane do programu Microsoft Excel i za pomocą tabel przestawnych, możliwość **Grupowania (wersja zapoznawcza) w siatkach** tabelarycznych, zależna od nowej funkcji kontroli siatki, umożliwia użytkownikom organizowanie swoich danych tabelarycznych w interesujący sposób aplikacjach finansowych i operacyjnych. Ponieważ ta funkcja rozszerza funkcję **Obliczone wartości**, **Grupowanie** pozwala uzyskać miarodajny wgląd w dane dzięki dostarczaniu obliczonych wartości (na przykład sum częściowych) na poziomie grupy.

[![Grupowanie danych w siatce.](./media/grids-groupingWithTotals.png)](./media/grids-groupingWithTotals.png)

Aby skorzystać z tej funkcji, kliknij prawym przyciskiem myszy kolumnę, według której chcesz grupować, a następnie wybierz polecenie **Grupuj według tej kolumny**. Ta akcja spowoduje posortowanie danych według wybranej kolumny, dodanie nowej kolumny **Grupy według** do początku do siatki, a następnie wstawienie „wierszy nagłówka” na początku każdej grupy. Te wiersze nagłówka zawierają następujące informacje o każdej grupie:

- Wartość danych dla grupy 
- Nazwa kolumny (te informacje są szczególnie przydatne, gdy istnieje wiele poziomów grupowania)
- Liczba wierszy danych w tej grupie
- Obliczane wartości dla dowolnej skonfigurowanej kolumny (na przykład sumy częściowe, jeśli kolumna jest skonfigurowana do pokazywania sumy)

Mając włączoną opcję [Zapisane widoki](saved-views.md), możesz zapisać grupowanie jako część widoku na stronach, które pozwalają na zapisywanie zapytań do widoków. Na przykład te, które mają duże selektory widoku. Więcej szczegółów znajdziesz w sekcji [Przełączanie między widokami](saved-views.md#switching-between-views). 

### <a name="multiple-levels-of-grouping"></a>Wiele poziomów grupowania
Po zgrupowaniu danych według jednej kolumny można je pogrupować według innej kolumny, zaznaczając w żądanej kolumnie opcję **Grupuj według tej kolumny**. Ten proces można powtarzać aż do uzyskania 5 zagnieżdżonych poziomów grupowania, co jest maksymalną obsługiwaną głębokością. W tym momencie nie będzie już można grupować według dodatkowych kolumn.

W dowolnym momencie można usunąć grupowanie według dowolnej kolumny, klikając prawym przyciskiem myszy tę kolumnę i wybierając polecenie **Rozgrupuj**. Można również usunąć grupowanie ze wszystkich kolumn, wybierając kolejno polecenia **Opcje siatki** i **Rozgrupuj wszystko**.

### <a name="sorting-grouped-data"></a>Sortowanie zgrupowanych danych
Po zgrupowaniu danych według jednej lub więcej kolumn możesz zmienić kierunek sortowania dla każdej kolumny grupującej poprzez odpowiedni nagłówek kolumny. 

Grupowanie pozostanie niezmienione w przypadku sortowania według kolumny niegrupowej. Dane sortowane są w obrębie każdej grupy na podstawie wybranej kolumny.

### <a name="expanding-and-collapsing-groups"></a>Rozwijanie i zwijanie grup
Początkowe grupowanie danych będzie miało rozwinięte wszystkie grupy. Podsumowane widoki danych można tworzyć, zwijając poszczególne grupy, a także rozwijając grupę i zwijając ją, aby ułatwić nawigację między danymi. Aby rozwinąć lub zwinąć grupę, wybierz przycisk pagonu (>) w odpowiednim wierszu nagłówka grupy. Należy pamiętać, że stan rozwijania/zwijania poszczególnych grup **nie jest** zapisywany w obszarze Personalizacja.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Zaznaczanie i odznaczanie wierszy na poziomie grupy
W taki sam sposób, w jaki można wybrać (lub usunąć zaznaczenie) wszystkie wiersze w siatce — zaznaczając pole wyboru u góry pierwszej kolumny w siatce — można również szybko zaznaczyć (lub usunąć zaznaczenie) wszystkich wierszy w grupie, zaznaczając pole wyboru w odpowiednim wierszu nagłówka grupy. Pole wyboru w wierszu nagłówka grupy zawsze odzwierciedla bieżący stan zaznaczenia wierszy w tej grupie, niezależnie od tego, czy zaznaczono wszystkie wierszy, nie zaznaczono wierszy lub wybrano tylko niektóre wiersze.

### <a name="hiding-column-names"></a>Ukrywanie nazw kolumn
Podczas grupowania danych domyślnym zachowaniem jest wyświetlenie nazwy kolumny w wierszu nagłówka grupy. Można wybrać opcję wyłączania nazwy kolumny w wierszach nagłówka grupy, wybierając **Opcje siatki** > **Ukryj nazwę kolumny grupy**.

### <a name="grouping-on-date-and-time-columns"></a>Grupowanie w kolumnach daty i godziny
Podczas grupowania według pól Data lub Data i godzina masz możliwość grupowania według roku, miesiąca lub dnia. Grupa „wartość” w odpowiednim wierszu nagłówka będzie odpowiadać formatowi z tego pola. Dodatkowo, dla pól DateTime i Time możesz grupować według godziny, minuty lub sekundy.

> [!IMPORTANT]
> Użytkownicy nie mogą obecnie dodać kolumny grupowania po zgrupowaniu w segmencie kolumny daty lub czasu.

## <a name="freezing-columns"></a>Zamrażanie kolumn
Niektóre kolumny w siatce mogą być na tyle ważne dla kontekstu, że nie powinny być przewijane w widoku. Zamiast tego możesz chcieć, aby wartości w tych kolumnach były zawsze widoczne. Funkcja **Zamrożenie kolumn w siatce** zapewnia użytkownikom tę elastyczność. 

[![Zamrażanie kolumn w siatce.](./media/gridFreezingColumns-07-25-2022.gif)](./media/gridFreezingColumns-07-25-2022.gif)

Aby zamrozić kolumnę, kliknij prawym przyciskiem myszy nagłówek kolumny, a następnie wybierz polecenie **Zamroź kolumnę**. Gdy ten krok zostanie ukończony po raz pierwszy, wybrana kolumna stanie się pierwszą kolumną i nie będzie już przewijana w widoku. Każda kolejna zamrożona kolumna zostanie dodana po prawej stronie ostatniej zamrożonej kolumny. W celu zmiany kolejności zamrożonych kolumn można użyć standardowych funkcji przenoszenia. Jednak zamrożonych kolumn nie można przenieść, aby były widoczne wśród zestawu odmrożonych kolumn. Podobnie odmrożonych kolumn nie można przenieść, aby były widoczne wśród zestawu zamrożonych kolumn.

Aby odmrozić kolumnę, kliknij prawym przyciskiem myszy nagłówek zamrożonej kolumny, a następnie wybierz polecenie **Odmroź kolumnę**. 

Należy zauważyć, że wybór wierszy i kolumny stanu wiersza w nowej siatce są zawsze zamrożone jako pierwsze dwie kolumny. Dlatego kiedy te kolumny są zawarte w siatce, zawsze będą widoczne dla użytkowników, niezależnie od pozycji przewijania w poziomie w siatce. Nie można zmienić kolejności tych dwóch kolumn.

## <a name="autofit-column-width"></a>Automatyczne dopasowanie szerokości kolumny
Podobnie jak w programie Excel, użytkownicy mogą wymusić automatyczną zmianę rozmiaru kolumny na podstawie zawartości, która jest w niej aktualnie wyświetlana. Wystarczy dwukrotnie nacisnąć (lub dwukrotnie kliknąć) obsługę zmiany rozmiaru w kolumnie. Można również umieścić fokus w nagłówku kolumny, a następnie **wybrać klucz A** (do automatycznego ustawienia).

## <a name="frequently-asked-questions"></a>Często zadawane pytania
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Jak włączyć formant nowej siatki w środowisku? 

Funkcja **Kontrolka nowej siatki** jest dostępna bezpośrednio w module Zarządzanie funkcjami w dowolnym środowisku. Po włączeniu tej funkcji w Zarządzaniu funkcjami wszystkie kolejne sesje użytkowników będą korzystać z nowej kontroli siatki. 

Ta funkcja rozpoczęła się domyślnie w wersji 10.0.21. Ma on zostać obowiązkowy w październiku 2022 roku.

## <a name="developer-topics"></a>Tematy dewelopera

### <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Deweloper] Rezygnacja z używania nowej siatki dla poszczególnych stron 
Jeśli Twoja organizacja odkryje stronę, na której występują pewne problemy z wykorzystaniem nowej siatki, dostępny jest interfejs API, który umożliwia indywidualnemu formularzowi korzystanie ze starszej kontroli sieci, jednocześnie zezwalając reszcie systemu na korzystanie z nowej kontroli sieci. Aby wycofać pojedynczą stronę z nowej siatki, należy dodać następujący wpis wywołania `super()` w metodzie `run()` dla formularza.

```this.forceLegacyGrid();```

Ten interfejs API zostanie ostatecznie wycofany, aby umożliwić usunięcie starszego formantu siatki. Jednak pozostanie on dostępny przez przynajmniej 12 miesięcy po jego zakończeniu. Jeśli jakiekolwiek problemy wymagają użycia tego interfejsu API, należy zgłosić je do rozwiązania Microsoft.

#### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Wymuszanie strony do korzystania z nowej siatki po wcześniejszym zrezygnowaniu z siatki
Jeśli użytkownik zrezygnował z używania nowej siatki przez pojedynczą stronę, można później ponownie włączyć nową siatkę po rozwiązaniu podstawowych problemów. Aby to zrobić, wystarczy usunąć połączenie do `forceLegacyGrid()`. Zmiana zostanie wniesienie w życie dopiero po wystąpieniu jednej z następujących sytuacji:

- **Ponowne wdrożenie środowiska**: Gdy środowisko jest aktualizowane i ponownie rozmieszczane, tabela, która przechowuje strony, które zrezygnowały z nowej siatki (FormControlReactGridState) jest automatycznie czyszczona.
- **Ręczne czyszczenie tabeli**: W przypadku scenariuszy rozwoju należy użyć języka SQL, aby wyczyścić tabelę FormControlReactGridState, a następnie ponownie uruchomić system AOS. Ta kombinacja akcji spowoduje zresetowanie buforowania stron, które zrezygnowały z nowej siatki.

### <a name="developer-opting-individual-grids-out-of-the-typing-ahead-of-the-system-capability"></a>[Deweloper] Wyłączanie poszczególnych kratek z możliwości systemu Pisanie przed systemem
Pojawiły się pewne scenariusze, które nie nadają się do współpracy z *Pisanie przed systemem*. (Na przykład, jakiś kod, który jest wyzwalany, gdy wiersz jest weryfikowany powoduje, że badanie źródła danych jest wyzwalane, a badanie może wtedy uszkodzić niezaangażowane edycje istniejących wierszy). Jeśli Twoja organizacja odkryje taki scenariusz, dostępne jest API, które pozwala programiście na wyłączenie asynchronicznego sprawdzania poprawności wierszy w poszczególnych siatkach i przywrócenie dotychczasowego zachowania.

Kiedy asynchroniczna walidacja wierszy jest wyłączona w siatce, użytkownicy nie mogą utworzyć nowego wiersza lub przejść do innego istniejącego wiersza w siatce, gdy występują problemy z walidacją w bieżącym wierszu. Efektem ubocznym tego działania jest to, że tabele nie mogą być wklejane z Excela do siatek aplikacjach finansowych i operacyjnych.

Aby wyłączyć indywidualną siatkę z asynchronicznego sprawdzania poprawności wierszy, dodaj następujące wywołanie po `super()` w metodzie `run()` formularza.

```<gridControl>.allowPreemptiveClient(false);```

> [!NOTE]
> - To wezwanie powinno być przywoływane tylko w wyjątkowych przypadkach i nie powinno być normą dla wszystkich krat.
> - Nie zalecamy przełączania tego API w czasie działania po załadowaniu formularza.

### <a name="developer-size-to-available-width-columns"></a>[Deweloper] Kolumny od rozmiaru do dostępnej szerokości
Jeśli projektant ustawi właściwość **WidthMode** na **SizeToAvailable** dla kolumn w nowej siatce, te kolumny mają początkowo taką samą szerokość, jaką miałyby w przypadku ustawienia właściwości na **SizeToContent**. Jednak rozciągają się one na użycie dowolnej dodatkowej szerokości w siatce. Jeśli właściwość jest ustawiona jako **SizeToAvailable** dla wielu kolumn, wszystkie te kolumny mają dowolną dodatkową szerokość w siatce. Jeśli jednak użytkownik ręcznie zmieni rozmiar jednej z tych kolumn, kolumna stanie się statyczna. Pozostanie on o tej samej szerokości i nie będzie już rozciągany, aby uzyskać dodatkową szerokość siatki.

### <a name="developer-specifying-the-column-that-receives-the-initial-focus-when-new-rows-are-created-by-using-the-down-arrow-key"></a>[Deweloper] Określanie kolumny, która otrzymuje początkowy fokus podczas tworzenia nowych wierszy za pomocą klawisza strzałki w dół
Jak omówiono w [różnicach podczas wprowadzania danych przed sekcją systemową](#differences-when-entering-data-ahead-of-the-system), jeśli jest włączona funkcja „Wpisanie z wyprzedzeniem” i użytkownik tworzy nowy wiersz za pomocą klawisza **strzałki w dół**, domyślnym zachowaniem jest umieść fokus w pierwszej kolumnie nowego wiersza. To doświadczenie może różnić się od możliwości w starszej siatce lub po wybraniu **przycisku Nowy**.

Użytkownicy i organizacje mogą tworzyć zapisane widoki, które są zoptymalizowane pod kątem wprowadzania danych. (Można na przykład zmienić kolejność kolumn, tak aby pierwsza kolumna rozpoczynała wprowadzanie danych) Ponadto na wersji 10.0.29 organizacje mogą dostosować to zachowanie za **pomocą metody selectedControlOnCreate()**. Ta metoda pozwala programiście określić kolumnę, która powinna otrzymać początkowy fokus podczas tworzenia nowego wiersza za pomocą klawisza **strzałki w dół**. Jako dane wejściowe ten interfejs API przyjmuje identyfikator formantu odpowiadający kolumnie, która powinna otrzymać zespół początkowy.

### <a name="developer-handling-grids-with-non-react-extensible-controls"></a>[Deweloper] Obsługa siatek za pomocą formantów innych niż React
Jeśli siatka jest wczytywana, system napotka rozszerzalny formant, który nie jest oparty na React, system wymusi renderowanie w starszej siatce. Gdy użytkownik po raz pierwszy napotka tę sytuację, zostanie wyświetlony komunikat oznaczający, że trzeba odświeżyć stronę. Następnie ta strona będzie automatycznie ładować starszą siatkę bez żadnych dodatkowych powiadomień dla użytkowników do czasu następnej aktualizacji systemu. 

Aby rozwiązać tę sytuację na stałe, autor rozszerzalnych formantów może utworzyć wersję React formantu do użycia w siatce.  Po określeniu klasy X++ dla formantu można użyć atrybutu **FormReactControlAttribute**, aby określić lokalizację pakietu React do załadowania dla tego formantu. Przykładem jest klasa `SegmentedEntryControl`.  

## <a name="known-issues"></a>Znane problemy
Ta sekcja zawiera listę znanych problemów związanych z nową kontrolą siatki.

### <a name="open-issues"></a>Otwarte problemy
- Po włączeniu funkcji **Kontrolka nowej siatki** niektóre strony będą nadal korzystać z istniejącej kontrolki siatki. Ma to miejsce w następujących sytuacjach:
 
    - [Rozwiązany] Problem 762533: Nieoczekiwany błąd klienta podczas wybierania wiersza na liście kart.
    - [Rozwiązane] Na stronie, która jest renderowana w wielu kolumnach, istnieje lista kart.
        - Ten typ listy kart jest obsługiwany przez **Nowy formant siatki** od wersji 10.0.30. W tym celu można usunąć dowolne użycia właściwości forceLegacyGrid(). 
    - [Rozwiązane] Na stronie istnieje lista zgrupowanych kart.
        - Pogrupowane listy kart są obsługiwana przez **Nowy formant siatki** od wersji 10.0.30. W tym celu można usunąć dowolne użycia właściwości forceLegacyGrid(). 
    - [Rozwiązane] Kolumna siatkowa z niereagującą, rozszerzalną kontrolą.
        - Formanty rozszerzalne mogą dostarczać wersję React swoich formantów, które zostaną załadowane po umieszczeniu w siatce i dostosowaniu definicji formantu do załadowania tego formantu, gdy jest używany w siatce. Aby uzyskać więcej informacji, zajrzyj do odpowiedniej sekcji dla deweloperów. 

    Gdy użytkownik po raz pierwszy napotka jedną z tych sytuacji, zostanie wyświetlony komunikat o odświeżeniu strony. Po wyświetleniu tego komunikatu strona będzie nadal wykorzystywać istniejącą siatkę dla wszystkich użytkowników, aż do następnej aktualizacji wersji produktu. Lepsza obsługa tych scenariuszy, dzięki czemu może być wykorzystywana nowa siatka, będzie brana pod uwagę podczas przyszłej aktualizacji.

- [KB 4582758] Rekordy są zamazane po zmianie powiększenia ze 100 na dowolną inną wartość procentową

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

