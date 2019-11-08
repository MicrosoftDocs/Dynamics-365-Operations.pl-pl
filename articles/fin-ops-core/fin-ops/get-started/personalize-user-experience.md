---
title: Personalizowanie środowiska użytkownika
description: W tym temacie wyjaśniono, jak można spersonalizować aplikację.
author: jasongre
manager: AnnBe
ms.date: 10/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 124609041163bbcaf1b86a6964fa3f56fcd8f755
ms.sourcegitcommit: 574309903f15eeab7911091114885b5c7279d22a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2019
ms.locfileid: "2658767"
---
# <a name="personalize-the-user-experience"></a>Personalizowanie środowiska użytkownika

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie wyjaśniono, jak można spersonalizować aplikację.

Istnieją trzy podstawowe klasy personalizacji.

- Personalizacje wprowadzane na stronie ustawień. Przykładami są motyw kolorów i strefa czasowa.
- Personalizacje związane z użyciem strony. Takie personalizacje są nazywane personalizacjami *niejawnymi*. Na przykład system przechowuje informacje o szerokość kolumn siatki, jeśli je zmienisz, oraz o rozwiniętych lub zwiniętych skróconych kartach.
- Personalizacje dokonywane przez użytkownika w wyglądzie strony poprzez zmianę sposobu wyświetlania lub działania elementu na stronie, często w trybie personalizacji interaktywnej. Takie personalizacje są nazywane personalizacjami *jawnymi*. Na przykład użytkownik może dodać, ukryć lub zmieniać elementy na stronie.

Każda personalizacja, którą użytkownik wprowadzi, dotyczy wyłącznie tego użytkownika, bez względu na typ personalizacji ani firmę, na której obecnie użytkownik wykonuje operacje. Zmiany, które użytkownik wprowadza na stronie, nie mają wpływu na innych użytkowników w systemie.

## <a name="system-wide-options-for-the-current-user"></a>Opcje dla bieżącego użytkownika, dotyczące całego systemu

Strona **Opcje użytkownika** zawiera kilka ustawień ogólnosystemowych dla bieżącego użytkownika. Aby otworzyć stronę **Opcje użytkownika**, na pasku nawigacji wybierz ikonę **Ustawienia** (symbol koła zębatego), a następnie wybierz opcję **Opcje użytkownika**. Strona **Opcje użytkownika** zawiera cztery karty z różnymi ustawieniami użytkownika:

- **Wygląd** — Umożliwia wybieranie motywu kolorów i domyślnego rozmiaru elementów na stronach.
- **Preferencje** — Umożliwia wybór domyślnych wartości, które będą używane przy każdym otwarciu w systemie. Wartości te dotyczą firmy, strony początkowej i domyślnego trybu wyświetlania/edycji. (Tryb wyświetlania/edycji określa, czy strona jest zablokowana do wyświetlania, czy otwarta do edycji po jej każdym otwarciu). Ta karta zawiera również opcje języka, strefy czasowej, daty, godziny oraz formatów liczb. Ponadto ta karta zawiera szereg różnych preferencji, które różnią się zależnie od wersji programu.
- **Konto** — Umożliwia podanie nazwy użytkownika i innych opcji związanych z kontem.
- **Przepływ pracy** — Umożliwia wybranie opcji związanych z przepływem pracy.

Oprócz możliwości zmian ustawień użytkownika, na stronie **Opcje użytkownika** można wyświetlić i usunąć swoje dane dotyczące użycia i personalizacji. Wystarczy wybrać **Dane dotyczące użycia** w okienku akcji

Podczas używania aplikacji wiele wyborów użytkownika jest zapamiętywanych, aby ułatwić użytkownikowi korzystanie z systemu w przyszłości. Na karcie **Personalizacja** można zobaczyć osobiste zmiany wprowadzone na stronach systemu przez użytkownika i zarządzać nimi. Na tej karcie można również zresetować objaśnienia funkcji (czyli okna podręczne, które wprowadzają nowe funkcje systemu). Następnie użytkownik zostanie ponownie ostrzeżony o wcześniej wykrytych funkcjach.

> [!NOTE]
> Jeśli funkcja [Zapisane widoki](saved-views.md) jest włączona, można wyświetlać personalizacje i zarządzać nimi, wybierając opcję **Personalizacja** w okienku akcji na stronie **Opcje użytkownika**.

## <a name="implicit-personalizations"></a>Personalizacje pośrednie

Personalizacje pośrednie to takie, które wykonuje się po prostu poprzez interakcję z określonymi funkcjami sterowania, które przechowują swój obecnie widoczny stan.

- **Kolumny w siatce** — Można dopasować szerokość kolumny w siatce, zaznaczając pasek zmiany rozmiaru znajdujący się po lewej lub po prawej stronie nagłówka kolumny, a następnie przesuwając go w lewo lub prawo, aż kolumna osiągnie żądaną odległość. Aplikacja przechowuje szerokość ustawioną dla kolumny. Następnie zmienia rozmiar kolumny na tę szerokość po następnym otwarciu strony zawierającej tę siatkę.
- **Skrócone karty** — Niektóre strony mają rozwijane sekcje nazywane *skróconymi kartami*. Aplikacja przechowuje informacje o skróconych kartach, który zostały rozwinięte i zwinięte. Po następnym otwarciu strony te same skrócone karty będą rozwinięte lub zwinięte, zależnie od ostatniej interakcji ze stroną. W niektórych przypadkach można przyspieszyć działanie systemu poprzez zwinięcie skróconej karty, bo aplikacja nie musi pobierać informacji zawartych w tej skróconej karcie, dopóki nie zostanie ona rozwinięta. Jak wyjaśniono dalej w tym temacie, można również zmienić kolejność skróconych kart na stronie.
- **Pola faktów** — na niektórych stronach znajduje się okienko **Informacje pokrewne**, w którym są wyświetlane informacje tylko do odczytu, które są związane z bieżącym tematem strony. Każda sekcja w okienku pola **Informacje pokrewne** jest znana jako *Pole informacji*. Można rozwinąć lub zwinąć całe okienko **Informacje pokrewne**, a także rozwinąć lub zwinąć poszczególne pola informacji. Aplikacja przechowuje te preferencje. Następnie po każdym otwarciu strony zostanie przywrócony stan rozwinięty lub zwinięty okienka **Informacje pokrewne** i poszczególnych pól informacji, zgodnie z ostatnią interakcją ze stroną. W niektórych przypadkach można przyspieszyć działanie systemu poprzez zwinięcie pola informacji, bo aplikacja nie musi pobierać informacji zawartych w tym polu informacji, dopóki nie zostanie ona rozwinięta.
- **Okienek akcji** — *Okienko akcji* pojawia się u góry większości stron. Okienko akcji zawiera przyciski dla wielu czynności, które można wykonywać na bieżącej stronie. Przyciski te często są pogrupowane na kartach. Można „przypiąć” otwarte całe okienko akcji lub ustawić jego domyślne zwinięcie. Po następnym otwarciu strony okienko akcji będzie otwarte lub zwinięte, zależnie od ostatniej interakcji ze stroną. Jeśli przypięto okienko akcji otwarte, zostanie wyświetlona ostatnio użyta karta.
- **Szybkie filtry** — *Szybki filtr* pojawia się nad wieloma siatkami. Szybki filtr umożliwia filtrowanie siatki na podstawie wybranej kolumny. Aplikacja przechowuje informacje o kolumnie, według której filtrowano. Przy następnym otwarciu strony zawierającej tę siatkę siatka będzie filtrowana według tej samej kolumny. Potem można filtrować siatkę według innej kolumny.
- **Filtry nagłówków kolumn** — Podczas filtrowania siatki za pomocą *kolumna nagłówków filtrów* można zmienić operator filtra w wymagany sposób, aby znaleźć żądane dane. Na przykład można zmienić operator z **zaczyna się od** na **wynosi dokładnie**. Po każdym użyciu filtra nagłówka kolumny i zmienić operatora filtra aplikacja zapisuje zmiany. Zostanie przywrócony operator filtra następnym razem, gdy będziesz filtrować według tej kolumny.
- **Okienko nawigacji** — Można otworzyć *okienko nawigacji*, naciskając przycisk **Rozwiń okienko nawigacji** w lewej górnej części strony. (Ten przycisk jest czasami nazywany przyciskiem _**Menu**_, *hamburgerem*, *menu hamburgerowym* lub *przyciskiem hamburgerowym*). Można przypiąć okienko nawigacji w stanie otwarcia lub zachować je domyślnie zwinięte. Po przypięciu otwartego okienka nawigacji aplikacja zachowa jego otwarcie do czasu, aż je zwiniesz.

## <a name="explicit-personalizations"></a>Personalizacje bezpośrednie

Różne osoby i firmy mają różne punkty widzenia na to, które dane są dla nich najważniejsze oraz na dane, które nie są im potrzebne w ich konkretnej działalności gospodarczej. Można dostosować sposób porządkowania i używania informacji. Można również określić, że pewna informacja ma być ukryta. Funkcje te są kluczowe dla indywidualnych potrzeb i stanowią przykłady jawnych personalizacji. Personalizacje bezpośrednie to te, które wykonujesz jawnie z zamiarem zmiany wyglądu lub zachowania elementu albo strony.

### <a name="shortcut-menu-options"></a>Opcje w menu skrótów

Menu skrótów oferują kilka sposobów bezpośredniego modyfikowania strony w celu jej dopasowania do wymagań własnych lub firmy. (Menu skrótów jest również nazywane *menu rozwijanym prawym przyciskiem myszy* lub *menu kontekstowym*).

Niektóre z najbardziej typowych i ważnych zmiany, jakie użytkownicy wprowadzają na stronach, są dostępne bezpośrednio jako opcje w menu skrótów. Na przykład począwszy od aktualizacji platformy 17 jeśli chcesz dodać lub ukryć kolumny w siatce, po prostu kliknij prawym przyciskiem myszy nagłówek kolumny, a następnie wybierz polecenie **Dodaj kolumny** lub **Ukryj tę kolumnę**.

Ponadto większość podstawowych typów personalizacji jawnych jest dostępnych po kliknięciu elementu prawym przyciskiem myszy i wybraniu polecenia **Personalizuj**. (Pamiętaj, że nie wszystkie elementy na stronie można personalizować). Podczas używania tej metody personalizacji pojawi się okno właściwości elementu.

![Personalizowanie właściwości elementu](./media/personalization-element-properties.png)

Okno właściwości służy do spersonalizowania elementu na następujące sposoby:

- Zmień etykietę elementu.
- Ukrycie elementu, tak aby nie był wyświetlany na stronie. Dane w polu nie zostały usunięte lub zmodyfikowane. Informacje nie są już wyświetlane na stronie.
- Umieszczenie informacji w sekcji podsumowania skróconej karty (jeśli element znajduje się na skróconej karcie).
- Pomiń pole, aby nigdy nie otrzymywało fokusu po przeliczeniu na stronę.
- Uniemożliwianie edytowania danych w polu (dla jakiegokolwiek rekordu).

Okno właściwości może zawierać inne możliwości personalizacji w zależności od elementu. Na przykład okno właściwości kafelka może pozwalać przenieść kafelek do pulpitu nawigacyjnego, a okno właściwości pulpitu nawigacyjnego może pozwalać utworzyć nowy obszar roboczy w tym pulpicie nawigacyjnym.

### <a name="the-personalization-toolbar"></a>Pasek narzędzi personalizacji

eJeśli chcesz wprowadzić wiele zmian na stronie lub wprowadzić zmiany, które nie są dostępne za pośrednictwem innego mechanizmu (np. zmiany kolejności elementów), można użyć pasek narzędzi **Personalizacja**. Aby otworzyć pasek narzędzi **Personalizacja**, wykonaj następujące kroki:

- Wybierz opcję **Personalizuj ten formularz** w oknie właściwości elementu.
- Wybierz **Personalizuj ten formularz** w grupie **Personalizacja** na karcie **Opcje** okienka akcji jakiejkolwiek strony.
- Wybierz przycisk **ustawienia** (symbol koła zębatego) na pasku nawigacyjnym, a następnie wybierz opcję **Personalizuj**.

[![Pasek narzędzi personalizacji](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Nawigacja po stronie

Gdy pasek narzędzi **Personalizacja** jest otwarty, Strona podstawowa jest tylko do odczytu (innymi słowy, nie można edytować danych), ale nadal jest interaktywna. W szczególności można rozwijać lub zwijać okienko **Informacje pokrewne**, przełączać karty oraz rozwijać lub zwijać sekcje, tak samo jak te akcje są zwykle wykonywane na stronie. Aby zastosować zmianę personalizacyjną do zwijanej sekcji lub karty (np. w celu ukrycia skróconej karty), należy wybrać przycisk, który pojawi się obok tej sekcji lub karty po umieszczeniu na niej fokusu za pomocą klawiaturę lub umieszczenia nad nią wskaźnika myszy.

#### <a name="personalization-tools"></a>Narzędzia personalizacji

Następujące narzędzia są dostępne na pasku narzędzi **Personalizacja**:

- Użyj narzędzia **Wybierz**, aby wybrać i zmienić właściwości elementu. Aby skorzystać z tego narzędzia, należy zaznaczyć przycisk **Wybierz** na pasku narzędzi, a następnie wybrać żądany element. Pojawi się okno właściwości elementu, w którym można zmienić dowolne właściwości tego elementu. Można powtórzyć ten proces dla innych elementów, które można personalizować na stronie. Należy pamiętać, że niektóre właściwości personalizacji mogą być niedostępne w niektórych scenariuszach. Na przykład nie można zamknąć pola, które jest wymagane.
- Użyj narzędzia **Ukryj**, aby ukryć element na tej stronie. Aby skorzystać z tego narzędzia, należy zaznaczyć przycisk **Ukryj** na pasku narzędzi, a następnie wybrać element do ukrycia. Używając narzędzia **Ukryj** w zacieniowanym kontenerze zostaną pokazane wszystkie elementy, które są obecnie ukryte. Można wówczas wyświetlić element, zaznaczając go. Aby zobaczyć, jak strona będzie wyglądała po ukryciu elementów, przełącz się na inne narzędzie do personalizacji.

    Można ukrywać wymagane pola i sekcje zawierające pola wymagane. W ten sposó pozwala to utworzyć uproszczone środowisko, w którym nie są wyświetlane wymagane pola o wartościach ustawianych domyślnie przez logikę biznesową. Ukryte pola wymagane staną się tymczasowo widoczne, jeśli są puste, gdy użytkownik spróbuje zapisać stronę.

- Wybierz narzędzie **Dodaj pole**, aby dodać pole do strony. Korzystając z tego narzędzia, można dodawać tylko pola, które są częścią definicji strony. Aby uzyskać informacje o tworzeniu nowych pól, które nie są częścią bieżącej definicji strony, zobacz [Pola niestandardowe](user-defined-fields.md). Po wybraniu przycisku **Dodaj pole** na pasku narzędzi należy najpierw zaznaczyć grupę lub obszar, gdzie chcesz dodać pole. W oknie dialogowym zostanie wyświetlona lista pól powiązanych z wybraną grupą lub obszarem. W oknie dialogowym zaznacz jedno lub więcej pól, które mają zostać dodane, a następnie kliknij opcję **Wstaw**. Aby usunąć pole, które zostało wcześniej dodane, należy powtórzyć proces, ale należy usunąć zaznaczenie tego pola w oknie dialogowym.
- Użyj narzędzia **Przenieś**, aby przenieść element w inne miejsce w bieżącej grupie elementów. Nie można przenieść elementu poza jego grupę nadrzędną. Aby skorzystać z tego narzędzia, należy zaznaczyć przycisk **Przenieś** na pasku narzędzi, a następnie wybrać element do przeniesienia. Po wybraniu elementu aplikacja określa lokalizację, dokąd można przenieść element. Te lokalizacje są nazywane *strefami upuszczania*. Podczas przeciągania elementu w granicach bieżącej grupy każda sfera upuszczania jest wyświetlana za pomocą kolorowej, pogrubionej linii obok obszaru, w którym można upuścić element.
- Użyj narzędzia **Pomiń**, aby usunąć element z sekwencji tabulacji na stronie. Po wybraniu przycisku **Pomiń** na pasku narzędzi w zacieniowanym kontenerze wyświetlone zostaną wszystkie elementy, które zostały pominięte. Można interaktywnie usunąć lub dodać pola do sekwencji kart.
- Użyj narzędzia **Pokaż w nagłówku**, aby wyświetlić pole w sekcji podsumowania skróconej karty. Po wybraniu przycisku **Pokaż w nagłówku** na pasku narzędzi w zacieniowanym kontenerze wyświetlone zostaną wszystkie pola, które wybrano jako pola podsumowania. Można dodać w interaktywny sposób pola do podsumowania skróconej karty lub je wybrać, by je z niego usunąć.
- Użyj narzędzia **Zablokuj**, aby oznaczyć element jako edytowalny lub nieedytowalny. Po wybraniu przycisku **Zablokuj** na pasku narzędzi w zacieniowanym kontenerze wyświetlone zostaną wszystkie elementy, które są nieedytowalne. Następnie można znowu umożliwić ich edycję. Należy zwrócić uwagę, że niektóre pola są wymagane i nie można ich oznaczyć jako nieedytowalne. Obok tych pól widać symbol kłódki.
- Użyj przycisku **Dodaj aplikację PowerApp**, aby na stronie osadzić aplikację utworzoną przy użyciu usługi Microsoft PowerApps. Aby uzyskać szczegółowe informacje o osadzaniu aplikacji usługi PowerApps w stronie, zobacz [Osadzanie aplikacji PowerApps](embed-power-apps.md).
- Użyj narzędzia **Wyczyść**, aby zresetować stronę do domyślnego stanu poinstalacyjnego. Zostaną usunięte wszystkie personalizacje na bieżącej stronie. Nie ma akcji Cofnij. Dlatego użyj tego narzędzia tylko wtedy, jeśli masz pewność, że chcesz zresetować stronę.
- Użyj narzędzia **Import**, aby wczytać personalizację z pliku utworzonego wcześniej przez siebie lub inną osobę. Podczas importowania personalizacji strony można określić, czy mają być dodawane do strony, czy zastępować wszystkie istniejące dla niej personalizacje. Nie ma akcji Cofnij. Dlatego po zaimportowaniu personalizacji należy ręcznie usunąć lub cofnąć wszelkie niepotrzebne zmiany.
- Użyj narzędzia **Eksport**, aby zapisać swoje personalizacje strony do pliku. Personalizacje można następnie udostępniać innym użytkownikom. Użytkownicy muszą zaimportować plik zawierający Twoje dane personalizacji strony.
- Wybierz przycisk **Zamknij**, aby zamknąć pasek narzędzi **Personalizacja** i przywrócić pierwotny interaktywny stan strony.

Zazwyczaj podczas korzystania z paska narzędzi **Personalizacja** Twoje personalizacje są uwzględniane zaraz po ich wprowadzeniu. Jeśli jednak funkcja [Zapisanych widoków](saved-views.md) jest włączona, należy jawnie zapisać personalizacje w wybranym widoku.

W niektórych przypadkach po wybraniu narzędzia obok elementu pojawia się ikona kłódki. Ten symbol wskazuje, że nie można zmodyfikować właściwości elementu, które są związane z wybranym narzędziem, ponieważ zmiany tych właściwości uniemożliwią poprawne działanie strony.

### <a name="adding-a-tile-list-or-link-to-a-workspace"></a>Dodawanie kafelka, listy lub łącza do obszaru roboczego

W przypadku niektórych stron zawierających listy funkcja **Dodaj do personalizacji** obszaru roboczego jest dostępna w grupie **Personalizacja** na karcie **Opcje** w okienku akcji. Ta funkcja umożliwia wypychanie ważnych informacji z bieżącej listy do określonego obszaru roboczego. Informacje wyświetlane w obszarze roboczym mogą być oparte na całej liście lub przefiltrowanej i posortowanej wersji listy. Można również określić, czy informacje mają być wyświetlane w obszarze roboczym w postaci listy, jako kafelek z podsumowaniem podającym liczbę przedmiotów na liście czy jako link.

> [!NOTE]
> Jeśli funkcja [Zapisane widoki](saved-views.md) jest włączona, zawartość przekazana do obszaru roboczego jest bezpośrednio połączona z widokiem. Kwerenda w widoku służy do pobierania danych w obszarze roboczym, a odpowiadający jej fragment lub łącze w obszarze roboczym powoduje otwarcie strony w tym widoku, dzięki czemu zostanie do niej zastosowany sposób wykonywania kwerend i personalizacji widoku.

[![Dodaj do obszaru roboczego](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Aby dodać listę do obszaru roboczego, najpierw należy prze sortować lub przefiltrować listę na stronie, tak aby informacje były wyświetlane tak, jak mają być widoczne w obszarze roboczym. (Jeśli funkcja zapisanych widoków jest włączona, nie można kontynuować, dopóki nie zapiszesz widoku, który ma te warunki.) Następnie wybierz opcję **Dodaj do obszaru roboczego**. Wybierz obszar roboczy, a następnie w polu **Prezentacja** wybierz opcję **Lista**. Po naciśnięciu przycisku **Konfiguruj** pojawi się okno dialogowe, w którym można wybrać kolumny, jakie mają być wyświetlane na liście w obszarze roboczym. Także można wybrać etykietę dla listy w obszarze roboczym.
- Aby dodać kafelek do obszaru roboczego, najpierw przefiltruj listę, tak aby przedstawiała dane, które mają być podsumowane lub chcesz mieć do nich szybki dostęp. (Jeśli funkcja zapisanych widoków jest włączona, nie można kontynuować, dopóki nie zapiszesz widoku, który ma te warunki.) Następnie wybierz opcję **Dodaj do obszaru roboczego**. Wybierz obszar roboczy, a następnie w polu **Prezentacja** wybierz opcję **Kafelek**. Po naciśnięciu przycisku **Konfiguruj** pojawi się okno dialogowe, gdzie można określić etykietę, która ma być używana dla kafelka w obszarze roboczym. Można również określić, czy na kafelku ma się pojawić liczba elementów. Po dodaniu kafelka do obszaru roboczego można go wybrać, aby otworzyć bieżącą stronę z obszaru roboczego. Następnie można wyświetlić przefiltrowaną listę, która jest skojarzona z kafelkiem.
- Aby dodać łącze do obszaru roboczego, najpierw należy przefiltrować listę na stronie tak, aby pokazywała interesujące Cię dane. (Jeśli funkcja zapisanych widoków jest włączona, nie można kontynuować, dopóki nie zapiszesz widoku, który ma te warunki.) Następnie wybierz opcję **Dodaj do obszaru roboczego**. Wybierz obszar roboczy, a następnie w polu **Prezentacja** wybierz opcję **Łącze**. Po naciśnięciu przycisku **Konfiguruj** pojawi się okno dialogowe, gdzie można określić etykietę, która ma być używana dla łącza. Można też opcjonalnie dodać do nowej sekcji etykietę zawierającą ten link.

Po dodaniu listy, kafelka lub łącza do obszaru roboczego można otworzyć ten obszar roboczy i dowolnie zmienić w nim kolejność elementów.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Dodawanie podsumowania z obszaru roboczego do pulpitu nawigacyjnego

Niektóre obszary robocze zawierają kafelki z liczbami i często je również warto umieścić na pulpicie nawigacyjnym. W obszarze roboczym kliknij prawym przyciskiem myszy kafelek z liczbą, wybierz opcję **Personalizacja**, a następnie w okienku właściwości kafelka wybierz opcję **Przypnij do pulpitu nawigacyjnego**. Następnym razem, kiedy otworzysz wybrany pulpit nawigacyjnego i odświeżysz go, ta liczba zostanie wyświetlona poniżej kafelka nawigacji dla tego obszaru roboczego. Można wybrać tę liczbę, aby przejść bezpośrednio do danych, które reprezentuje.

### <a name="personalizing-your-dashboard"></a>Personalizowanie pulpitu nawigacyjnego

Pulpit nawigacyjny jest często pierwszą stroną, którą widzisz po uruchomieniu aplikacji. Pulpit nawigacyjny można dostosować, tak aby pokazywane w nim były tylko potrzebne kafelki obszaru roboczego. Ponadto można zmienić kolejność wyświetlania kafelków w dowolny pożądany sposób, zmienić nazwy kafelków nawigacji obszaru roboczego lub dodać nowy kafelek do obszaru roboczego.

Aby spersonalizować pulpit nawigacyjny, kliknij prawym przyciskiem myszy dowolny kafelek, a następnie wybierz **Personalizacja**, aby otworzyć okno właściwości kafelka.

- Jeśli chcesz ukryć wybrany kafelek lub zmienić jego nazwę, można dokonać tej zmiany bezpośrednio w oknie właściwości.
- Aby zapisać kafelki obszaru roboczego, wybierz opcję **Personalizuj ten formularz** w oknie właściwości, aby wyświetlić pasek narzędzi **Personalizacji**. Następnie można uporządkować dowolnie kafelki za pomocą narzędzia **Przenieś**.
- Aby dodać nowy kafelek obszaru roboczego, w oknie właściwości zaznacz **Dodaj obszar roboczy**. W dolnej części pulpitu nawigacyjnego jest tworzony nowy kafelek obszaru roboczego. Ten kafelek obszaru roboczego można zmieniać dowolnie. Można również dodać listy, kafelki oraz linki do obszaru roboczego w sposób opisany w sekcji tego tematu pt. [Dodawanie list, kafelków lub linków do obszarów roboczych](#adding-a-tile-list-or-link-to-a-workspace).

## <a name="administration-of-personalizations"></a>Administrowanie personalizacjami

Po spersonalizowaniu strony można udostępnić te personalizacje innym użytkownikom poprzez wyeksportowanie spersonalizowanej strony. Następnie możesz poprosić innych użytkowników, aby otworzyli spersonalizowaną stronę i zaimportowali utworzony przez Ciebie plik personalizacji. Alternatywnie można przekazać swoje personalizacje użytkownikowi posiadającemu uprawnienia administratora. Ten użytkownik może następnie zastosować Twój plik personalizacji do wielu użytkowników w tym samym czasie.

Użytkownicy posiadający uprawnienia administratora mogą też zarządzać personalizacjami dla innych użytkowników na stronie **Personalizacja**.

W przypadku użytkowników, którzy nie włączyli funskcji [Zapisane widoki](saved-views.md), na tej stronie znajdują się cztery karty:

- **Zastosuj** — ta opcja pozwala zaimportować lub wybrać personalizację dla co najmniej jednego użytkownika. Aby zastosować personalizację dla jednego lub kilku użytkowników, należy najpierw zaznaczyć rolę i użytkowników, którzy pełnią tę rolę. Następnie wybierz istniejącą personalizację do zastosowania do wybranych użytkowników lub zaimportuj plik personalizacji. Personalizacja jest zweryfikowana i zostanie zastosowana do wszystkich zaznaczonych użytkowników następnym razem, gdy otworzą wybraną stronę.
- **Wyczyść** — Tutaj można wyczyścić wszystkie personalizacje strony lub obszaru roboczego dla jednego lub więcej użytkowników. Najpierw wybierz stronę lub obszar roboczy, aby wyświetlić listę użytkowników, którzy spersonalizowali tę stronę/obszar. Następnie wybierz użytkowników, dla których chcesz wyczyścić personalizację danej strony lub obszaru roboczego, i wybierz opcję **Wyczyść**. Wszystkie personalizacje zastosowane przez wybranych użytkowników do wybranej strony lub obszaru roboczego zostaną usunięte. Tej operacji nie można cofnąć. Jednak jeśli dla strony lub obszaru roboczego zapisano personalizację, można ją ponownie zaimportować.
- **Użytkownicy** — Wybierz użytkownika, aby wyświetlić listę stron spersonalizowanych przez tę osobę. Następnie można włączyć lub wyłączyć dla wybranego użytkownika możliwość korzystania z personalizacji określonych stron lub całego systemu. Można również zaimportować, wyeksportować lub wyczyścić personalizację dla wybranego użytkownika. Ponadto można zresetować objaśnienia funkcji dla użytkownika. W takim przypadku, jeśli użytkownik wyłączył wszystkie okna wyskakujące, które wprowadzają nowe funkcje, pojawią się ponownie przy następnym napotkaniu tych funkcji przez użytkownika.
- **System** — ta opcja pozwala tymczasowo wyłączyć personalizacje dla wszystkich użytkowników w systemie. W takim przypadku wszystkie personalizacje są usuwane dla wszystkich użytkowników, a wszystkie strony są resetowane do ich stanu domyślnego. W przypadku ponownego włączenia personalizacji wszystkie personalizacje zostaną zastosowane ponownie. Można również trwale usunąć wszystkie personalizacje dla wszystkich użytkowników w systemie. Nie jest możliwe odzyskanie personalizacji, które zostały usunięte. Dlatego przed wykonaniem tego zadania należy koniecznie wyeksportować wszystkie personalizacje, które potem możesz chcieć zaimportować.

W przypadku użytkowników, którzy nie włączyli funkcji [Zapisane widoki](saved-views.md), na stronie **Personalizacje** znajduje się pięć kart:

- **Opublikowane widoki** — te widoki zostały opublikowane w organizacji. Aby zmienić użytkowników, którzy są ukierunkowani na te widoki, można zmienić role zabezpieczeń lub firmy skojarzone z poszczególnymi widokami. Można również eksportować lub usuwać jeden lub więcej opublikowanych widoków.
- **Nieopublikowane widoki** — te widoki to widoki szablonów, które zostały zaimportowane do systemu, ale nie zostały jeszcze opublikowane. Te widoki można publikować, eksportować i usuwać.
- **Widoki osobiste** — te widoki zostały utworzone przez użytkowników w systemie. Możesz opublikować widok osobisty w organizacji lub skopiować jeden lub więcej z tych widoków do innego użytkownika. Te widoki można również eksportować i usuwać wedle potrzeb.
- **Użytkownicy** — Wybierz użytkownika, aby wyświetlić listę stron spersonalizowanych przez tę osobę. Następnie można włączyć lub wyłączyć dla wybranego użytkownika możliwość korzystania z personalizacji określonych stron lub całego systemu. Można również zaimportować, wyeksportować lub wyczyścić personalizację dla wybranego użytkownika. Ponadto można zresetować objaśnienia funkcji dla użytkownika. W takim przypadku, jeśli użytkownik wyłączył wszystkie okna wyskakujące, które wprowadzają nowe funkcje, pojawią się ponownie przy następnym napotkaniu tych funkcji przez użytkownika.
- **System** — ta opcja pozwala tymczasowo wyłączyć personalizacje dla wszystkich użytkowników w systemie. W takim przypadku wszystkie personalizacje są usuwane dla wszystkich użytkowników, a wszystkie strony są resetowane do ich stanu domyślnego. W przypadku ponownego włączenia personalizacji wszystkie personalizacje zostaną zastosowane ponownie. Można również trwale usunąć wszystkie personalizacje dla wszystkich użytkowników w systemie. Nie jest możliwe odzyskanie personalizacji, które zostały usunięte. Dlatego przed wykonaniem tego zadania należy koniecznie wyeksportować wszystkie personalizacje, które potem możesz chcieć zaimportować.

Użytkownicy, którzy mają dostęp do strony **Personalizacje**, mogą również importować widoki osobiste lub szablony za pomocą przycisku **Importuj widoki** w okienku akcji.

## <a name="personalizing-inventory-dimensions"></a>Personalizacja wymiarów magazynowych

W przypadku personalizowania konfiguracji wymiarów magazynowych na stronie należy wziąć pod uwagę ustawienia utworzone przy użyciu opcji **Wyświetl wymiary**. Na przykład można użyć personalizacji w celu ukrycia kolumny dla wymiaru zapasów Numer partii, ale kolumna pojawi się przy następnym otwarciu strony. To zachowanie występuje, ponieważ ustawienia **Wyświetlanie wymiarów** sterują wyświetlanymi kolumnami wymiaru zapasów. Ustawienia w sekcji **Wyświetlanie wymiarów** mają zastosowanie do wszystkich stron i zastępują wszelkie spersonalizowane konfiguracje pól wymiarów magazynowych na poszczególnych stronach.

Tym samym w poprzednim przykładzie, jeśli nie chcesz wyświetlania kolumny dla wymiaru inwentaryzacji numeru partii na stronie, musisz wyczyścić ten wymiar w ramach opcji tabeli **Wyświetl wymiary** dla tej strony.
