---
title: Personalizowanie środowiska użytkownika
description: W tym temacie wyjaśniono, jak można spersonalizować aplikację.
author: jasongre
manager: AnnBe
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e46c392c43b63ef443f66d8ea8f9e91a9df3d126
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693239"
---
# <a name="personalize-the-user-experience"></a>Personalizowanie środowiska użytkownika

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak można spersonalizować aplikację i omówiono następujące zagadnienia: 

- **Opcje dotyczące całego systemu** — te opcje personalizacji są wykonywane na stronie ustawień i są dostępne dla wszystkich użytkowników. Przykładami są motyw kolorów i strefa czasowa. 
- **Ograniczony dostęp do personalizacji** — na tym poziomie dostępu akcje użytkownika, które są związane z typowym użytkowaniem strony, są automatycznie zapisywane przez aplikację i przywracane po następnym odwiedzeniu strony. Na przykład aplikacja przechowuje informacje o szerokość kolumn siatki, jeśli je zmienisz, oraz o rozwiniętych lub zwiniętych skróconych kartach. 
- **Pełny dostęp do personalizacji** — na tym poziomie dostępu użytkownicy mają dostęp do wszystkich możliwości personalizacji w aplikacji. W szczególności mają dostęp do paska narzędzi **Personalizacja**. 
- **Personalizacje udostępniania** — Użytkownicy dysponujący pełnym dostępem do personalizacji mogą eksportować personalizacje stron i udostępniać je innym użytkownikom.
- **Administrowanie personalizacjami** — Użytkownicy uprzywilejowani mogą uzyskać dostęp do strony administracji **Personalizacja**, aby zarządzać wszystkimi personalizacjami na poziomie organizacyjnym. 

## <a name="system-wide-options-for-the-current-user"></a>Opcje dla bieżącego użytkownika, dotyczące całego systemu

Strona **Opcje użytkownika** zawiera kilka ustawień ogólnosystemowych dla bieżącego użytkownika. Te opcje są dostępne dla wszystkich użytkowników, nawet użytkowników, którzy nie uzyskali dostępu do personalizacji. Aby otworzyć stronę **Opcje użytkownika**, na pasku nawigacji wybierz ikonę **Ustawienia**, a następnie wybierz opcję **Opcje użytkownika**. Strona **Opcje użytkownika** zawiera cztery karty z różnymi ustawieniami użytkownika:

- **Wygląd** — Umożliwia wybieranie motywu kolorów i domyślnego rozmiaru elementów na stronach.
- **Preferencje** — Umożliwia wybór domyślnych wartości, które będą używane przy każdym otwarciu w systemie. Wartości te dotyczą domyślnej firmy, strony początkowej i domyślnego trybu wyświetlania/edycji. (Tryb wyświetlania/edycji określa, czy strona jest zablokowana do wyświetlania, czy otwarta do edycji po jej każdym otwarciu). Ta karta zawiera również opcje języka, strefy czasowej, daty, godziny oraz formatów liczb. Ponadto ta karta zawiera szereg różnych preferencji, które różnią się zależnie od wersji programu.
- **Konto** — Wyświetl lub dostosuj swoją nazwę użytkownika i inne opcje związane z kontem.
- **Przepływ pracy** — Umożliwia wybranie opcji związanych z przepływem pracy.

Oprócz możliwości zmian ustawień użytkownika, można wyświetlić i usunąć swoje dane dotyczące użycia i personalizacji na stronie **Opcje użytkownika** . Aby wyświetlić dane użytkowe, wybierz opcję **Użycie danych** w okienku akcji. Na karcie **Personalizacja** można zobaczyć osobiste zmiany wprowadzone na stronach systemu przez użytkownika i zarządzać nimi. Na tej karcie można również zresetować objaśnienia funkcji (czyli okna podręczne, które wprowadzają nowe funkcje systemu). Następnie użytkownik zostanie ponownie ostrzeżony o wcześniej wykrytych funkcjach.

> [!NOTE]
> Jeśli funkcja [Zapisane widoki](saved-views.md) jest włączona, można wyświetlać personalizacje i zarządzać nimi, wybierając opcję **Personalizacja** w okienku akcji na stronie **Opcje użytkownika**.

## <a name="restricted-personalization-access-formerly-implicit-personalizations"></a>Ograniczony dostęp do personalizacji (dawniej personalizacja niejawna)

Na poziomie **Ograniczony dostęp do personalizacji** akcje użytkownika, które są związane z typowym użytkowaniem strony, są automatycznie zapisywane przez aplikację i przywracane po następnym odwiedzeniu strony. Nie jest wymagana jawna akcja zapisywania. 

Poniżej znajduje się lista akcji, które przypadają na typowe wykorzystanie strony i są objęte ograniczonym dostępem do personalizacji: 

- **Szerokości kolumn w siatce** — Można dopasować szerokość kolumny w siatce, zaznaczając pasek zmiany rozmiaru znajdujący się po lewej lub po prawej stronie nagłówka kolumny, a następnie przesuwając go w lewo lub prawo, aż kolumna osiągnie żądaną odległość. Aplikacja przechowuje szerokość ustawioną dla kolumny. Następnie następnym razem, gdy otworzysz tę stronę, rozmiar kolumny zostanie zmieniony na tę szerokość.
- **Stopka siatki i sumy kolumn** – *(Dostępne tylko wtedy, gdy jest włączona nowa kontrola sieci)* Można określić, czy suma ma być wyświetlana u dołu dowolnej kolumny numerycznej w siatce, a także czy stopka siatki powinna być widoczna. Aplikacja przechowuje te preferencje i stosuje je przy następnym otwarciu strony. Aby uzyskać dodatkowe informacje, zobacz [Zdolności siatki](grid-capabilities.md). 
- **Skrócone karty** — Niektóre strony mają rozwijane sekcje nazywane *skróconymi kartami*. Aplikacja przechowuje informacje o skróconych kartach, który zostały rozwinięte lub zwinięte. Po następnym otwarciu strony te same skrócone karty będą rozwinięte lub zwinięte, zależnie od ostatniej interakcji ze stroną. W niektórych przypadkach można przyspieszyć działanie systemu poprzez zwinięcie skróconej karty, bo aplikacja nie musi pobierać informacji zawartych w tej skróconej karcie, dopóki nie zostanie ona rozwinięta. Jak wyjaśniono dalej w tym temacie, można również zmienić kolejność skróconych kart na stronie.
- **Pola informacji** — na niektórych stronach znajduje się okienko **Informacje pokrewne**, w którym są wyświetlane informacje tylko do odczytu, które są związane z bieżącym tematem strony. Każda sekcja w okienku pola **Informacje pokrewne** jest znana jako *Pole informacji*. Można rozwinąć lub zwinąć całe okienko **Informacje pokrewne**, a także rozwinąć lub zwinąć poszczególne Pola informacji. Aplikacja przechowuje te preferencje. Następnie po każdym otwarciu strony zostanie przywrócony stan rozwinięty lub zwinięty okienka **Informacje pokrewne** i poszczególnych Pól informacji, zgodnie z ostatnią interakcją ze stroną. W niektórych przypadkach można przyspieszyć działanie systemu poprzez zwinięcie okienka **Informacje pokrewne** lub pola informacji, bo aplikacja nie musi pobierać informacji zawartych w tym polu informacji, dopóki nie zostanie ona rozwinięta.
- **Okienek akcji** — *Okienko akcji* pojawia się u góry większości stron. Okienko akcji zawiera przyciski dla wielu czynności, które można wykonywać na bieżącej stronie. Przyciski te często są pogrupowane na kartach. Można *przypiąć* otwarte całe okienko akcji lub ustawić jego domyślne zwinięcie. Po następnym otwarciu strony okienko akcji będzie otwarte lub zwinięte, zależnie od ostatniej interakcji ze stroną. Jeśli przypięto okienko akcji otwarte, zostanie wyświetlona ostatnio użyta karta.
- **Szybkie filtry** — *Szybki filtr* pojawia się nad wieloma siatkami. Szybki filtr umożliwia filtrowanie siatki na podstawie pojedyńczej wybranej kolumny. Aplikacja przechowuje informacje o kolumnie, według której filtrowano. Następnie następnym razem, gdy otworzysz tę stronę, siatka użyje tej samej kolumny do domyślnego filtrowania. Potem można wciąż filtrować siatkę według innej kolumny.
- **Filtry nagłówków kolumn** — Podczas filtrowania siatki za pomocą *kolumna nagłówków filtrów* można zmienić operator filtra w wymagany sposób, aby znaleźć żądane dane. Na przykład można zmienić operator z **zaczyna się od** na **wynosi dokładnie**. Po każdym użyciu filtra nagłówka kolumny i zmienić operatora filtra aplikacja zapisuje zmiany. Zostanie przywrócony operator filtra następnym razem, gdy będziesz filtrować według tej kolumny.
- **Okienko nawigacji** — Można otworzyć *okienko nawigacji*, naciskając przycisk **Rozwiń okienko nawigacji** w lewej górnej części strony. (Ten przycisk jest czasami nazywany przyciskiem _**Menu**_, *hamburgerem*, *menu hamburgerowym* lub *przyciskiem hamburgerowym*). Można przypiąć okienko nawigacji w stanie otwarcia lub zachować je domyślnie zwinięte. Po przypięciu otwartego okienka nawigacji aplikacja zachowa jego otwarcie do czasu, aż je zwiniesz.

## <a name="full-personalization-access-formerly-explicit-personalizations"></a>Pełny dostęp do personalizacji (dawniej personalizacja jawna)

Na poziomie **pełny dostęp do personalizacji** użytkownicy mają dostęp do wszystkich funkcji personalizacji, które zapewnia aplikacja. Ponieważ różne osoby i firmy mają różne potrzeby podczas interakcji z aplikacją, zwłaszcza jeśli chodzi o używane pola, personalizacja zapewnia narzędzia, które pozwalają użytkownikom i organizacjom dostosować sposób porządkowania informacji i interakcji z aplikacją. Te możliwości są kluczowe dla zapewnienia uproszczonych, zoptymalizowanych środowisk w aplikacji, dostosowanych do Ciebie i Twojej organizacji. 

Jeśli funkcja [zapisane widoki](saved-views.md) jest włączona, jest wymagane jawne zapisanie w celu utrwalenia tych zmian w określonym widoku. Gdy funkcja **Zapisanych widoków** jest wyłączona, zmiany te są zapisywane automatycznie.

W poniższych sekcjach omówiono zakres możliwości personalizacji, które są dostępne dla użytkowników na poziomie **pełnego dostępu do personalizacji**. Oto wybrane możliwości:

- Opcje w menu skrótów
- Pasek narzędzi **Personalizacji**
- Dodawanie kafelków, list i łączy do obszarów roboczych
- Dodawanie podsumowania z obszaru roboczego do pulpitu nawigacyjnego
- Personalizowanie pulpitu nawigacyjnego

### <a name="shortcut-menu-options"></a>Opcje w menu skrótów

Menu skrótów to jeden ze sposobów zmiany interfejsu strony, tak aby lepiej spełniał Twoje wymagania lub wymagania Twojej organizacji. (Menu skrótów jest również nazywane *menu rozwijanym prawym przyciskiem myszy* lub *menu kontekstowym*).

Niektóre z najbardziej typowych i ważnych zmiany, jakie użytkownicy wprowadzają na stronach, są dostępne bezpośrednio jako opcje w menu skrótów. Na przykład jeśli chcesz dodać lub ukryć kolumny w siatce, po prostu kliknij prawym przyciskiem myszy nagłówek kolumny, a następnie wybierz polecenie **Wstaw kolumny** lub **Ukryj tę kolumnę**.

Ponadto większość podstawowych typów personalizacji jest dostępnych po kliknięciu elementu prawym przyciskiem myszy i wybraniu polecenia **Personalizuj**. (Pamiętaj, że nie wszystkie elementy na stronie można personalizować). Podczas używania tej metody personalizacji pojawi się *okno właściwości* elementu.

![Personalizowanie właściwości elementu](./media/cli-element-property-window.png)

Okno właściwości służy do spersonalizowania elementu na następujące sposoby:

- Zmień etykietę elementu.
- Ukrycie elementu, tak aby nie był wyświetlany na stronie. Dane w polu nie zostały usunięte lub zmodyfikowane. Informacje po prostu nie są już wyświetlane na stronie.
- Umieszczenie informacji w sekcji podsumowania skróconej karty (jeśli element znajduje się na skróconej karcie).
- Pomiń pole, aby nigdy nie otrzymywało fokusu po przeliczeniu na stronę.
- Uniemożliwianie edytowania danych w polu (dla jakiegokolwiek rekordu).
- Umożliwia wskazanie pola wymaganego do wprowadzania danych. Jeśli w tym polu nie wprowadzono żadnej wartości, zostanie ono wyświetlone przy użyciu czerwonego obramowania oraz gwiazdki, aby wskazać ten stan. Ta opcja jest dostępna tylko w wersji 10.0.11, gdy włączone są [Zapisane widoki](saved-views.md) i **Wyznacz pola wymagane użycia funkcji personalizacji**.

Okno właściwości może zawierać inne możliwości personalizacji w zależności od elementu. Na przykład okno właściwości kafelka może umożliwiać promowanie tego kafelka do pulpitu nawigacyjnego, a okna właściwości elementów na domyślnym pulpicie nawigacyjnym mogą umożliwiać tworzenie nowego niestandardowego obszaru roboczego.

### <a name="the-personalization-toolbar"></a>Pasek narzędzi personalizacji

eJeśli chcesz wprowadzić wiele zmian na stronie lub wprowadzić zmiany, które nie są dostępne za pośrednictwem innych mechanizmów (np. zmiany kolejności elementów), można użyć pasek narzędzi **Personalizacja**. Aby otworzyć pasek narzędzi **Personalizacja**, wykonaj następujące kroki:

- Wybierz kombinację klawiszy **Ctrl + Shift + P** z dowolnego elementu na stronie.
- Wybierz opcję **Personalizuj tę stronę** w oknie właściwości elementu.
- Wybierz **Personalizuj ten formularz** w grupie **Personalizacja** na karcie **Opcje** okienka akcji jakiejkolwiek strony.
- Wybierz przycisk **ustawienia** (symbol koła zębatego) na pasku nawigacyjnym, a następnie wybierz opcję **Personalizuj**.

[![Pasek narzędzi personalizacji](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Nawigacja po stronie

Gdy pasek narzędzi **Personalizacja** jest otwarty, Strona podstawowa jest tylko do odczytu (innymi słowy, nie można edytować danych), ale nadal jest interaktywna. W szczególności można rozwijać lub zwijać okienko **Informacje pokrewne**, przełączać karty oraz rozwijać lub zwijać sekcje, tak samo jak te akcje są zwykle wykonywane na stronie. Aby zastosować zmianę personalizacyjną do zwijanej sekcji lub karty (np. w celu ukrycia skróconej karty), należy wybrać przycisk, który pojawi się obok tej sekcji lub karty po umieszczeniu na niej fokusu za pomocą klawiaturę lub umieszczenia nad nią wskaźnika myszy.

#### <a name="personalization-tools"></a>Narzędzia personalizacji

Następujące narzędzia są dostępne na pasku narzędzi **Personalizacja**:

- Użyj narzędzia **Wybierz**, aby wybrać i zmienić właściwości elementu. Aby skorzystać z tego narzędzia, należy zaznaczyć przycisk **Wybierz** na pasku narzędzi, a następnie wybrać żądany element. Pojawi się okno właściwości elementu, w którym można zmienić dowolne właściwości tego elementu. Można powtórzyć ten proces dla innych elementów, które można personalizować na stronie. Należy pamiętać, że niektóre właściwości personalizacji mogą być niedostępne w niektórych scenariuszach. Na przykład nie można zamknąć pola, które jest wymagane.
- Użyj narzędzia **Ukryj**, aby ukryć element na tej stronie. Aby skorzystać z tego narzędzia, należy zaznaczyć przycisk **Ukryj** na pasku narzędzi, a następnie wybrać element do ukrycia. Używając narzędzia **Ukryj** w zacieniowanym kontenerze zostaną pokazane wszystkie elementy, które są obecnie ukryte. Można wówczas wyświetlić element, zaznaczając go. Aby zobaczyć, jak strona będzie wyglądała po ukryciu elementów, przełącz się na inne narzędzie do personalizacji lub zamknąć pasek narzędzi personalizacji.
- Wybierz narzędzie **Dodaj pola**, aby dodać pola do strony. Korzystając z tego narzędzia, można dodawać tylko pola, które są częścią definicji strony. Aby uzyskać informacje o tworzeniu nowych pól, które nie są częścią bieżącej definicji strony, zobacz [Tworzenie pól niestandardowych i praca z nimi](user-defined-fields.md). Po wybraniu przycisku **Dodaj pola** na pasku narzędzi należy najpierw zaznaczyć siatkę lub sekcję, gdzie chcesz dodać pole. W oknie dialogowym zostanie wyświetlona lista pól powiązanych z wybraną siatkę lub sekcję. W oknie dialogowym zaznacz jedno lub więcej pól, które mają zostać dodane, a następnie kliknij opcję **Aktualizuj**. Aby usunąć pole, które zostało wcześniej dodane, należy powtórzyć proces, ale należy usunąć zaznaczenie tego pola w oknie dialogowym.
- Użyj narzędzia **Przenieś**, aby przenieść element w inne miejsce w bieżącej grupie elementów. Nie można przenieść elementu poza jego grupę nadrzędną. Aby skorzystać z tego narzędzia, należy zaznaczyć przycisk **Przenieś** na pasku narzędzi, a następnie wybrać element do przeniesienia. Po wybraniu elementu aplikacja określa lokalizację, dokąd można przenieść element. Te lokalizacje są nazywane *strefami upuszczania*. Podczas przeciągania elementu w granicach bieżącej grupy każda sfera upuszczania jest wyświetlana za pomocą kolorowej, pogrubionej linii obok obszaru, w którym można upuścić element.
- Użyj narzędzia **Pomiń**, aby usunąć element z sekwencji tabulacji na stronie. Po wybraniu przycisku **Pomiń** na pasku narzędzi w zacieniowanym kontenerze wyświetlone zostaną wszystkie elementy, które zostały pominięte. Można interaktywnie usunąć lub dodać pola do sekwencji kart.
- Użyj narzędzia **Pokaż w nagłówku**, aby wyświetlić pole w sekcji podsumowania skróconej karty. Po wybraniu przycisku **Pokaż w nagłówku** na pasku narzędzi w zacieniowanym kontenerze wyświetlone zostaną wszystkie pola, które wybrano jako pola podsumowania. Można dodać w interaktywny sposób pola do podsumowania skróconej karty lub je wybrać, by je z niego usunąć.
- Narzędzie **Wymaganie** umożliwia wyznaczenie elementu jako wymaganego do wprowadzania danych. Po wybraniu przycisku **Wymagane** na pasku narzędzi w zacieniowanym kontenerze wyświetlone zostaną wszystkie elementy, które zostały spersonalizowane, aby były wymagane. Następnie można oznaczyć je jako niewymagane. Ta opcja jest dostępna tylko w wersji 10.0.12 i późniejsze, gdy włączone jest funkcja **Wyznacz pola wymagane użycia funkcji personalizacji**.
- Użyj narzędzia **Zablokuj**, aby oznaczyć element jako edytowalny lub nieedytowalny. Po wybraniu przycisku **Zablokuj** na pasku narzędzi w zacieniowanym kontenerze wyświetlone zostaną wszystkie elementy, które są nieedytowalne. Następnie można znowu umożliwić ich edycję. Należy zwrócić uwagę, że niektóre pola są wymagane i nie można ich oznaczyć jako nieedytowalne. Obok tych pól widać symbol kłódki.
- Użyj narzędzia **Dodaj aplikację z Power Apps**, aby na stronie osadzić aplikację utworzoną przy użyciu usługi Microsoft Power Apps. Aby uzyskać szczegółowe informacje o osadzaniu aplikacji z usługi Power Apps w stronie, zobacz [Osadzanie aplikacji z Power Apps](embed-power-apps.md). Ta opcja jest dostępna tylko wtedy, gdy jest wyłączona funkcja [Zapisanych widoków](saved-views.md).
- Użyj przycisku **Dodaj aplikację**, by osadzić na stronie aplikację utworzoną za pomocą Microsoft Power Apps lub programu innej firmy. Ta opcja jest dostępna tylko wtedy, gdy jest włączona funkcja [Zapisanych widoków](saved-views.md). 
- Użyj narzędzia **Wyczyść**, aby zresetować stronę do domyślnego stanu poinstalacyjnego. Zostaną usunięte wszystkie personalizacje na bieżącej stronie. Nie możesz cofnąć tej czynności. Dlatego użyj tego narzędzia tylko wtedy, jeśli masz pewność, że chcesz zresetować stronę. Po włączeniu funkcji **Zapisanych widoków** narzędzie czyści personalizacje bieżącego widoku.
- Użyj narzędzia **Import**, aby wczytać personalizację z pliku utworzonego wcześniej przez siebie lub inną osobę. 

    - Po wyłączeniu funkcji **Zapisanych widoków** można wybrać, czy dodać lub zastąpić istniejące personalizacje personalizacjami, które są importowane na stronę. Nie możesz cofnąć tej czynności. Dlatego po zaimportowaniu personalizacji należy ręcznie usunąć lub cofnąć wszelkie niepotrzebne zmiany.
    - Gdy funkcja **Zapisane widoki** zostanie włączona, zaimportowane personalizacje staną się widokiem na stronie. Jeśli widok już istnieje, można pominąć import, zastąpić bieżący widok o tej samej nazwie lub zmienić nazwę widoku importowanego.

- Użyj narzędzia **Eksport**, aby zapisać swoje personalizacje strony do pliku. Personalizacje można następnie udostępniać innym użytkownikom. Użytkownicy muszą zaimportować plik zawierający Twoje dane personalizacji strony. Po włączeniu funkcji **Zapisanych widoków** to narzędzie zapisuje bieżący widok w pliku w celu udostępnienia.
- Wybierz przycisk **Zamknij**, aby zamknąć pasek narzędzi **Personalizacja** i przywrócić pierwotny interaktywny stan strony.

Zazwyczaj podczas korzystania z paska narzędzi **Personalizacja** Twoje personalizacje są uwzględniane zaraz po ich wprowadzeniu. Jeśli jednak funkcja [Zapisanych widoków](saved-views.md) jest włączona, należy jawnie zapisać personalizacje w wybranym widoku.

W niektórych przypadkach po wybraniu narzędzia obok elementu pojawia się ikona kłódki. Ten symbol wskazuje, że nie można zmodyfikować właściwości elementu, które są związane z wybranym narzędziem, ponieważ zmiany tych właściwości uniemożliwią poprawne działanie strony.

### <a name="adding-tiles-lists-and-links-to-a-workspace"></a>Dodawanie kafelków, list i łączy do obszaru roboczego

W przypadku niektórych stron zawierających listy funkcja **Dodaj do personalizacji** obszaru roboczego jest dostępna w grupie **Personalizacja** na karcie **Opcje** w okienku akcji. Ta funkcja umożliwia wypychanie ważnych informacji z bieżącej listy do określonego obszaru roboczego. Informacje wyświetlane w obszarze roboczym mogą być oparte na całej liście lub przefiltrowanej i posortowanej wersji listy. Można również określić, czy informacje mają być wyświetlane w obszarze roboczym w postaci listy, jako kafelek z podsumowaniem podającym liczbę przedmiotów na liście czy jako link.

> [!NOTE]
> Jeśli funkcja [Zapisane widoki](saved-views.md) jest włączona, zawartość przekazana do obszaru roboczego jest bezpośrednio połączona z widokiem. Kwerenda w widoku służy do pobierania danych do obszaru roboczego, a odpowiadający jej fragment lub łącze w obszarze roboczym powoduje otwarcie strony w tym widoku, dzięki czemu zostanie do niej zastosowany sposób wykonywania kwerend i personalizacji widoku. Jeśli widok zostanie zaktualizowany, odpowiednie elementy obszaru roboczego zostaną skorygowane do nowej definicji widoku.

[![Dodaj do obszaru roboczego](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Aby dodać listę do obszaru roboczego, najpierw należy prze sortować lub przefiltrować listę na stronie, tak aby informacje były wyświetlane tak, jak mają być widoczne w obszarze roboczym. (Jeśli funkcja **Zapisanych widoków** jest włączona, nie można kontynuować, dopóki nie zapiszesz widoku, który ma te warunki.) Następnie wybierz opcję **Dodaj do obszaru roboczego**. Wybierz obszar roboczy, a następnie w polu **Prezentacja** wybierz opcję **Lista**. Po naciśnięciu przycisku **Konfiguruj** pojawi się okno dialogowe, w którym można wybrać kolumny, jakie mają być wyświetlane na liście w obszarze roboczym. Także można wybrać etykietę dla listy w obszarze roboczym.
- Aby dodać kafelek do obszaru roboczego, najpierw przefiltruj listę, tak aby przedstawiała dane, które mają być podsumowane lub chcesz mieć do nich szybki dostęp. (Jeśli funkcja **Zapisanych widoków** jest włączona, nie można kontynuować, dopóki nie zapiszesz widoku, który ma te warunki.) Następnie wybierz opcję **Dodaj do obszaru roboczego**. Wybierz obszar roboczy, a następnie w polu **Prezentacja** wybierz opcję **Kafelek**. Po naciśnięciu przycisku **Konfiguruj** pojawi się okno dialogowe, gdzie można określić etykietę, która ma być używana dla kafelka w obszarze roboczym. Można również określić, czy na kafelku ma się pojawić liczba elementów. Po dodaniu kafelka do obszaru roboczego można go wybrać, aby otworzyć bieżącą stronę z obszaru roboczego. Następnie można wyświetlić przefiltrowaną listę, która jest skojarzona z kafelkiem.
- Aby dodać łącze do obszaru roboczego, najpierw należy przefiltrować listę na stronie tak, aby pokazywała interesujące Cię dane. (Jeśli funkcja **Zapisanych widoków** jest włączona, nie można kontynuować, dopóki nie zapiszesz widoku, który ma te warunki.) Następnie wybierz opcję **Dodaj do obszaru roboczego**. Wybierz obszar roboczy, a następnie w polu **Prezentacja** wybierz opcję **Łącze**. Po naciśnięciu przycisku **Konfiguruj** pojawi się okno dialogowe, gdzie można określić etykietę, która ma być używana dla łącza. Można też opcjonalnie dodać do nowej sekcji etykietę zawierającą ten link.

Po dodaniu listy, kafelka lub łącza do obszaru roboczego można otworzyć ten obszar roboczy i dowolnie zmienić w nim kolejność elementów.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Dodawanie podsumowania z obszaru roboczego do pulpitu nawigacyjnego

Niektóre obszary robocze zawierają kafelki z liczbami i często je również warto umieścić na pulpicie nawigacyjnym. W obszarze roboczym kliknij prawym przyciskiem myszy kafelek z liczbą, wybierz opcję **Personalizacja**, a następnie w okienku właściwości kafelka wybierz opcję **Przypnij do pulpitu nawigacyjnego**. Następnym razem, kiedy otworzysz pulpit nawigacyjnego (i odświeżysz go), ta liczba zostanie wyświetlona poniżej kafelka nawigacji dla tego obszaru roboczego. Można wybrać tę liczbę, aby przejść bezpośrednio do danych, które reprezentuje.

### <a name="personalizing-your-dashboard"></a>Personalizowanie pulpitu nawigacyjnego

Pulpit nawigacyjny jest często pierwszą stroną, którą widzisz po uruchomieniu aplikacji. Można je personalizować jak każdą inną stronę w systemie, korzystając z tych samych mechanizmów opisanych wcześniej w tym temacie. 

> [!WARNING]
> Obecnie Po ukryciu zawartości na pulpicie nawigacyjnym ważne jest bezpośrednie docelowanie kafelka, a nie obszaru wokół niego. Ukrycie grupy wokół kafelka może przynieść nieoczekiwane wyniki, jeśli kolejne kafelki zostaną dodane później lub jeśli system jest przełączany do innego języka.

Jedną z unikatowych możliwości personalizacji dostępnych na pulpicie nawigacyjnym jest możliwość dodawania kafelków. 

- Jeśli funkcja **Aplikacje całostronicowe** jest wyłączona, można dodać nowy kafelek, klikając prawym przyciskiem myszy element na pulpicie nawigacyjnym, a następnie wybierając polecenie **Dodaj obszar roboczy**. W dolnej części pulpitu nawigacyjnego jest tworzony nowy kafelek obszaru roboczego. Ten kafelek obszaru roboczego można zmieniać dowolnie. Można również dodać listy, kafelki oraz linki do obszaru roboczego w sposób opisany w sekcji tego tematu pt. [Dodawanie kafelków, list i łączy do obszaru roboczego](personalize-user-experience.md#adding-tiles-lists-and-links-to-a-workspace).
- Jeśli funkcja **Aplikacje całostronicowe** jest wyłączona, można dodać nowy kafelek, klikając prawym przyciskiem myszy element na pulpicie nawigacyjnym, a następnie wybierając polecenie **Dodaj aplikację**. W oknie dialogowym określ, czy chcesz dodać kafelek dla nowego obszaru roboczego czy kafelka z zawartością, który ma zawartość z Power Apps lub z witryny sieci Web. Następnie postępuj zgodnie z instrukcjami, aby skonfigurować wybraną opcję. W dolnej części pulpitu nawigacyjnego jest tworzony nowy kafelek. 

## <a name="sharing-personalizations"></a>Udostępnianie personalizacji

Po spersonalizowaniu strony można udostępnić te personalizacje innym użytkownikom poprzez wyeksportowanie spersonalizowanej strony. Następnie można poprosić innych użytkowników o zaimportowanie pliku personalizacji. Alternatywnie można przekazać swoje personalizacje użytkownikowi posiadającemu uprawnienia administratora. Użytkownik ten może następnie zastosować ten plik personalizacji do wielu użytkowników jednocześnie, korzystając ze strony administracji **Personalizacja**.

## <a name="administration-of-personalizations"></a>Administrowanie personalizacjami

Strona **Personalizacja** jest centralnym centrum zarządzania personalizacjami na poziomie organizacyjnym. Zawartość i możliwości na tej stronie zależą od tego, czy włączono funkcję **Zapisane widoki**.

Klienci, którzy włączyli funkcję **Zapisane widoki**, powinni zapoznać się z sekcją „Zarządzanie globalnie widokami” w temacie [Zapisane widoki](saved-views.md).

W przypadku użytkowników, którzy jeszcze nie włączyli funskcji [Zapisane widoki](saved-views.md), na tej stronie znajdują się cztery karty:

- **Zastosuj** — ta opcja pozwala zaimportować lub wybrać personalizację dla co najmniej jednego użytkownika. Aby zastosować personalizację dla jednego lub kilku użytkowników, należy najpierw zaznaczyć rolę i użytkowników, którzy pełnią tę rolę. Następnie wybierz istniejącą personalizację do zastosowania do wybranych użytkowników lub zaimportuj plik personalizacji. Personalizacja jest zweryfikowana i zostanie zastosowana do wszystkich zaznaczonych użytkowników następnym razem, gdy otworzą wybraną stronę.
- **Wyczyść** — Tutaj można wyczyścić wszystkie personalizacje strony lub obszaru roboczego dla jednego lub więcej użytkowników. Najpierw wybierz stronę lub obszar roboczy, aby wyświetlić listę użytkowników, którzy spersonalizowali tę stronę/obszar. Następnie wybierz użytkowników, dla których chcesz wyczyścić personalizację danej strony lub obszaru roboczego, i wybierz opcję **Wyczyść**. Wszystkie personalizacje zastosowane przez wybranych użytkowników do wybranej strony lub obszaru roboczego zostaną usunięte. Tej operacji nie można cofnąć. Jednak jeśli dla strony lub obszaru roboczego zapisano personalizację, można ją ponownie zaimportować.
- **Użytkownicy** — Wybierz użytkownika, aby wyświetlić listę stron spersonalizowanych przez tę osobę. Następnie można włączyć lub wyłączyć dla wybranego użytkownika możliwość korzystania z personalizacji określonych stron lub całego systemu. Można również zaimportować, wyeksportować lub wyczyścić personalizację dla wybranego użytkownika. Ponadto można zresetować objaśnienia funkcji dla użytkownika. W takim przypadku, jeśli użytkownik wyłączył wszystkie okna wyskakujące, które wprowadzają nowe funkcje, pojawią się ponownie przy następnym napotkaniu tych funkcji przez użytkownika.
- **System** — ta opcja pozwala tymczasowo wyłączyć personalizacje dla wszystkich użytkowników w systemie. W takim przypadku wszystkie personalizacje są usuwane dla wszystkich użytkowników, a wszystkie strony są resetowane do ich stanu domyślnego. W przypadku ponownego włączenia personalizacji wszystkie personalizacje zostaną zastosowane ponownie. Można również trwale usunąć wszystkie personalizacje dla wszystkich użytkowników w systemie. Nie jest możliwe odzyskanie personalizacji, które zostały usunięte. Dlatego przed wykonaniem tego zadania należy koniecznie wyeksportować wszystkie personalizacje, które potem możesz chcieć zaimportować.

## <a name="personalizing-inventory-dimensions"></a>Personalizacja wymiarów magazynowych

W przypadku personalizowania konfiguracji wymiarów magazynowych na stronie należy wziąć pod uwagę ustawienia utworzone przy użyciu opcji **Wyświetl wymiary**. Na przykład można użyć personalizacji w celu ukrycia kolumny dla wymiaru zapasów Numer partii, ale kolumna pojawi się przy następnym otwarciu strony. To zachowanie występuje, ponieważ ustawienia **Wyświetlanie wymiarów** sterują wyświetlanymi kolumnami wymiaru zapasów. Ustawienia w sekcji **Wyświetlanie wymiarów** mają zastosowanie do wszystkich stron i zastępują wszelkie spersonalizowane konfiguracje pól wymiarów magazynowych na poszczególnych stronach.

Tym samym w poprzednim przykładzie, jeśli nie chcesz wyświetlania kolumny dla wymiaru inwentaryzacji numeru partii na stronie, musisz wyczyścić ten wymiar w ramach opcji tabeli **Wyświetl wymiary** dla tej strony.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]