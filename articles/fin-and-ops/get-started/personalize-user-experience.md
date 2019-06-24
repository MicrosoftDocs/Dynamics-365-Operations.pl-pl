---
title: Personalizowanie środowiska użytkownika
description: W tym temacie wyjaśniono, jak można spersonalizować Microsoft Dynamics 365 for Finance and Operations.
author: jasongre
manager: AnnBe
ms.date: 05/17/2019
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
ms.openlocfilehash: 67ba1a95299de09c74e2fa2808cb63f61acf5862
ms.sourcegitcommit: c576b81dc3c93c09fb08fb0ba0c19f417360c5ab
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/05/2019
ms.locfileid: "1620021"
---
# <a name="personalize-the-user-experience"></a>Personalizowanie środowiska użytkownika

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak można spersonalizować Microsoft Dynamics 365 for Finance and Operations.

W programie Finance and Operations istnieją trzy podstawowe klasy personalizacji.

- Personalizacje wprowadzane na stronie Ustawienia. Przykładami są motyw kolorów i strefa czasowa.
- Personalizacje związane z używaniem stron, nazywane *niejawnymi* (domyślnymi/pośrednimi) personalizacjami. Na przykład Finance and Operations przechowuje informacje o szerokość kolumn siatki, jeśli je zmienisz, oraz o rozwiniętych lub zwiniętych skróconych kartach.
- Personalizacje dokonywane przez użytkownika w celu zmodyfikowania wyglądu strony poprzez zmianę sposobu wyświetlania lub działania elementu na stronie, często w trybie personalizacji interaktywnej. Takie personalizacje są nazywane personalizacjami *jawnymi* (bezpośrednimi). Na przykład użytkownik może dodać lub ukryć elementy albo zmienić ich kolejność na stronie.

Każda personalizacja, którą użytkownik wprowadzi w programie Finance and Operations, dotyczy wyłącznie tego użytkownika, bez względu na typ personalizacji ani firmę, na której obecnie użytkownik wykonuje operacje. Zmiany, które użytkownik wprowadza na stronie, nie mają wpływu na innych użytkowników w systemie.

## <a name="system-wide-options-for-the-current-user"></a>Opcje dla bieżącego użytkownika, dotyczące całego systemu

Strona **Opcje użytkownika** zawiera kilka ustawień ogólnosystemowych dla bieżącego użytkownika. Aby otworzyć stronę **Opcje użytkownika**, na pasku nawigacji wybierz menu **Ustawienia** (symbol koła zębatego), a następnie wybierz opcję **Opcje użytkownika**. Strona **Opcje użytkownika** zawiera cztery karty z różnymi ustawieniami użytkownika:

- **Wygląd** — Umożliwia wybieranie motywu kolorów i domyślnego rozmiaru elementów na stronach.
- **Preferencje** — Umożliwia wybór domyślnych wartości, które będą używane przy każdym otwarciu aplikacji Finance and Operations. Wartości te dotyczą firmy, strony początkowej i domyślnego trybu wyświetlania/edycji. (Tryb wyświetlania/edycji określa, czy strona jest zablokowana do wyświetlania, czy otwarta do edycji po jej każdym otwarciu). Ta karta zawiera również opcje języka, strefy czasowej, daty i godziny oraz formatu liczb. Ponadto ta karta zawiera szereg różnych preferencji, które różnią się zależnie od wersji programu.
- **Konto** — Umożliwia podanie nazwy użytkownika i innych opcji związanych z kontem.
- **Przepływ pracy** — Umożliwia wybranie opcji związanych z przepływem pracy.

Oprócz możliwości modyfikowania ustawień użytkownika, można wyświetlić i usunąć swoje dane dotyczące użycia i personalizacji, klikając przycisk **dane dotyczące użycia**. Podczas używania aplikacji wiele wyborów użytkownika jest zapamiętywanych, aby ułatwić użytkownikowi korzystanie z systemu w przyszłości. Karta **Personalizacja** umożliwia wyświetlanie osobistych zmian wprowadzonych na stronach systemu przez użytkownika i zarządzanie nimi. Objaśnienia funkcji, wyskakujące okienka przedstawiające nowe funkcje w produkcie (dostępne w aktualizacji platformy 26), również można zresetować na tej karcie, tak aby znowu otrzymywać alerty dotyczące funkcji napotkanych wcześniej.  

## <a name="implicit-personalizations"></a>Personalizacje pośrednie

Personalizacje pośrednie to takie, które wykonuje się po prostu poprzez interakcję z określonymi funkcjami sterowania, które „zapamiętują” swój obecnie widoczny stan.

- **Kolumny w siatce** — Można dopasować szerokość kolumny w siatce, zaznaczając pasek zmiany rozmiaru znajdujący się po lewej lub po prawej stronie nagłówka kolumny, a następnie przesuwając go w lewo lub prawo, aż kolumna osiągnie żądaną odległość. Program Finance and Operations przechowuje szerokość ustawioną dla kolumny. Następnie zmienia rozmiar kolumny na tę szerokość po każdym otwarciu strony zawierającej tę siatkę.
- **Skrócone karty** — Niektóre strony mają rozwijane sekcje nazywane *skróconymi kartami*. Program Finance and Operations przechowuje informacje o skróconych kartach, który zostały rozwinięte i zwinięte. Następnie po każdym powrocie do strony te same skrócone karty będą rozwinięte lub zwinięte, zależnie od ostatniej interakcji ze stroną. W niektórych przypadkach można przyspieszyć działanie systemu poprzez zwinięcie skróconej karty, bo program Finance and Operations nie musi pobierać informacji zawartych w tej karcie, dopóki nie zostanie ona rozwinięta. Jak wyjaśniono dalej w tym temacie, można również zmienić kolejność skróconych kart na stronie.
- **Pola informacji** — Niektóre strony mają sekcję nazywaną okienkiem *pola informacji*. To okienko zawiera informacje tylko do odczytu związane z tematem bieżącej strony. Każda sekcja w okienku pola informacji to *pole informacji*. Można ukryć lub wyświetlić całe okienko pola informacji, a także rozwinąć lub zwinąć poszczególne pola informacji. Program Finance and Operations przechowuje preferencje. Następnie po każdym powrocie do strony zostanie przywrócony stan okienka pola informacji i poszczególnych pól informacji, zgodnie z ostatnią interakcją ze stroną. W niektórych przypadkach można przyspieszyć działanie systemu poprzez zwinięcie pola informacji, bo program Finance and Operations nie musi pobierać informacji zawartych w tym polu, dopóki nie zostanie ono rozwinięte.
- **Okienek akcji** — *Okienko akcji* pojawia się u góry większości stron. Okienko akcji zawiera przyciski dla wielu czynności, które można wykonywać na bieżącej stronie. Przyciski te często są pogrupowane na kartach. Można przypiąć otwarte całe okienko akcji lub ustawić jego domyślne zwinięcie. Przy następnym otwarciu strony program Finance and Operations przywróci przypięty stan okienka akcji. Jeśli okienko akcji jest przypięte w stanie otwarcia, program Finance and Operations będzie także wyświetlał kartę z ostatnio wykonanymi akcjami.
- **Szybkie filtry** — *Szybki filtr* pojawia się nad wieloma siatkami. Szybki filtr umożliwia filtrowanie siatki na podstawie wybranej kolumny. Program Finance and Operations przechowuje informacje o kolumnie, według której filtrowano. Przy następnym otwarciu strony zawierającej tę siatkę siatka będzie filtrowana według tej samej kolumny. Potem można filtrować siatkę według innej kolumny.
- **Filtry nagłówków kolumn** — Podczas filtrowania siatki za pomocą *filtrów nagłówków kolumn* można zmienić operator filtra w wymagany sposób, aby znaleźć żądane dane. Na przykład można zmienić operator z **zaczyna się od** na **wynosi dokładnie**. Po każdym użyciu filtra nagłówka kolumny i zmodyfikowaniu operatora filtra program Finance and Operations zapisuje zmiany. Przywróci operator filtra następnym razem, gdy będziesz filtrować według tej kolumny.
- **Okienko nawigacji** — Można otworzyć *okienko nawigacji*, naciskając przycisk **Menu** w lewym okienku dowolnej strony. (Przycisk **Menu** jest czasami nazywany *hamburgerem*, *menu hamburgerowym* lub *przyciskiem hamburgerowym*). Można przypiąć okienko nawigacji w stanie otwarcia lub zachować je domyślnie zwinięte. Po przypięciu otwartego okienka nawigacji program Finance and Operations zachowa jego otwarcie do czasu, aż je zwiniesz.

## <a name="explicit-personalizations"></a>Personalizacje bezpośrednie

Różne osoby i firmy mają różne punkty widzenia na to, które dane są dla nich najważniejsze oraz na dane, które nie są im potrzebne w ich konkretnej działalności gospodarczej. W programie Finance and Operations można dostosować sposób porządkowania i używania informacji. Można również określić, że pewna informacja ma być ukryta. Funkcje te są kluczowe dla indywidualnych potrzeb i stanowią przykłady jawnych personalizacji. Personalizacje bezpośrednie to te, które wykonujesz jawnie z zamiarem zmiany wyglądu lub zachowania elementu albo strony.

### <a name="shortcut-menu-options"></a>Opcje w menu skrótów

Menu skrótów oferują kilka sposobów bezpośredniego modyfikowania strony w celu jej dopasowania do wymagań własnych lub firmy. (Menu skrótów jest również nazywane *menu rozwijanym prawym przyciskiem myszy* lub *menu kontekstowym*).

Niektóre z najbardziej typowych i ważnych zmiany, jakie użytkownicy wprowadzają na stronach, są dostępne bezpośrednio jako opcje w menu skrótów. Na przykład począwszy od aktualizacji platformy 17 jeśli chcesz dodać lub ukryć kolumny w siatce, po prostu kliknij prawym przyciskiem myszy nagłówek kolumny w siatce, a następnie wybierz polecenie **Dodaj kolumny** lub **Ukryj tę kolumnę**.

Ponadto większość podstawowych typów personalizacji jawnych jest dostępnych po kliknięciu elementu prawym przyciskiem myszy i wybraniu polecenia **Personalizuj**. (Pamiętaj, że nie wszystkie elementy na stronie można personalizować). Podczas używania tej metody personalizacji pojawi się okno właściwości elementu.

![Personalizowanie właściwości elementu](./media/personalization-element-properties.png)

Okno właściwości służy do spersonalizowania elementu na następujące sposoby:

- Zmień etykietę elementu.
- Ukrycie elementu, tak aby nie był wyświetlany na stronie. Dane w polu nie zostały usunięte lub zmodyfikowane. Informacje nie są już wyświetlane na stronie.
- Umieszczenie informacji w sekcji podsumowania na skróconej karcie (jeśli element znajduje się na skróconej karcie).
- Pomijanie pola po naciśnięciu klawisza Tab w celu przechodzenia między polami na stronie.
- Uniemożliwianie edytowania danych w polu (dla jakiegokolwiek rekordu).

Okno właściwości może zawierać inne możliwości personalizacji w zależności od elementu. Na przykład okno właściwości kafelka może pozwalać przenieść kafelek do pulpitu nawigacyjnego, a okno właściwości pulpitu nawigacyjnego może pozwalać utworzyć nowy obszar roboczy w tym pulpicie nawigacyjnym.

### <a name="the-personalization-toolbar"></a>Pasek narzędzi personalizacji

Jeśli chcesz wprowadzić wiele zmian na stronie lub wprowadzić zmiany, które nie są dostępne za pośrednictwem innych mechanizmów (np. zmiany kolejności elementów), można użyć pasek narzędzi **Personalizacja**. Aby otworzyć pasek narzędzi **Personalizacji** wybierz opcję **Spersonalizuj ten formularz** w oknie właściwości elementu. Można również wybrać pozycję **Spersonalizuj ten formularz** w grupie **Personalizacja** na karcie **Opcje** okienka akcji każdej ze stron.

[![Pasek narzędzi personalizacji](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Nawigacja po stronie

Możliwość nawigowanie na stronie w czasie, gdy jest otwarty pasek narzędzi **Personalizacja**, zależy od używanej wersji platformy.

- Przed aktualizacją platformy 19 podczas otwarcia paska narzędzi **Personalizacja** strona jest tylko do odczytu (nie można na niej nic wprowadzać) i nieinteraktywna (zmiany można wprowadzać tylko w widocznych elementach na stronie). Jeśli chcesz dokonać zmian elementów wewnątrz zwiniętej sekcji lub na innej karcie, należy zamknąć pasek narzędzi **Personalizacja**, rozwinąć sekcję lub przełączyć na żądaną kartę, a następnie otworzyć paska narzędzi **Personalizacja**.

- Począwszy od aktualizacji platformy 19 jeśli pasek narzędzi **Personalizacja** jest otwarty, strona wciąż będzie tylko do odczytu, ale jest znacznie bardziej interaktywna. W szczególności podczas otwarcia paska narzędzi **Personalizacja** można rozwinąć lub zwinąć okienko pola informacji, przełączać karty oraz rozwijać i zwijać sekcje w taki sam sposób, jak zwykle robi się to na stronie. Aby zastosować zmianę personalizacyjną do zwijanej sekcji lub karty (np. w celu ukrycia skróconej karty), należy nacisnąć przycisk, który pojawi się obok karty lub zwijanej sekcji po umieszczeniu na niej fokusu za pomocą klawiaturę lub umieszczenia nad nią wskaźnika myszy.

#### <a name="personalization-tools"></a>Narzędzia personalizacji

Następujące narzędzia są dostępne na pasku narzędzi **Personalizacja**:

- Użyj narzędzia **Wybierz**, aby wybrać i zmienić właściwości elementu. Wybierz narzędzie **Wybierz**, a następnie wybierz element, którego właściwości chcesz zmodyfikować. Po zaznaczeniu elementu pojawi się okno jego właściwości, w którym można zmienić dowolne właściwości tego elementu. Można powtórzyć ten proces dla innych elementów, które można personalizować na tej stronie. Jednak ze względu na sposób używania pewnych elementów program Finance and Operations nie pozwoli na zmianę ich niektórych właściwości. Dlatego po wybraniu elementu możesz zobaczyć, że niektórych jego właściwości nie można zmodyfikować. Na przykład nie można ukryć pola, które jest wymagane.
- Użyj narzędzia **Przenieś**, aby przenieść element w inne miejsce w bieżącej grupie elementów. (Nie można przenieść elementu poza jego grupę nadrzędną). Wybierz narzędzie **Przenieś**, a następnie wybierz element, który chcesz przenieść. Po wybraniu elementu rozwiązanie Finance and Operations przeskanuje stronę, aby określić, dokąd można przenieść element. Następnie tworzy serię „miejsc upuszczenia”. Podczas przeciągania elementu w granicach bieżącej grupy każde „miejsce upuszczania” jest wyświetlane za pomocą kolorowej, pogrubionej linii obok obszaru, w którym można upuścić element.
- Użyj narzędzia **Ukryj**, aby ukryć element na tej stronie. Wybierz narzędzie **Ukryj**, a następnie wybierz element, który chcesz ukryć. Po wybraniu narzędzia **Ukryj** w zacieniowanym kontenerze zostaną pokazane wszystkie elementy, które są obecnie ukryte. Następnie można je odkryć. Po wybraniu narzędzia **Zaznaczanie** można sprawdzić wygląd strony po ukryciu zaznaczonych elementów.

    - Począwszy od aktualizacji platformy 18 można ukrywać wymagane pola i sekcje zawierające pola wymagane. Pozwala to utworzyć uproszczone środowisko, w którym nie są wyświetlane wymagane pola o wartościach ustawianych domyślnie przez logikę biznesową. Wymagane pola ukryte również są tymczasowo pokazywane, gdy są puste w trakcie próby zapisu.

- Użyj narzędzia **Podsumowanie**, aby wyświetlić element w sekcji podsumowania skróconej karty. Narzędzie podsumowania ma zastosowanie tylko do pól w sekcji skróconej karty. Po wybraniu narzędzia **Podsumowanie** w zacieniowanym kontenerze wyświetlone zostaną wszystkie pola, które wybrano jako pola podsumowania. Można dodać w interaktywny sposób pola do podsumowania skróconej karty lub je wybrać, by je z niego usunąć.
- Użyj narzędzia **Pomiń**, aby usunąć element z sekwencji tabulacji na stronie. Po wybraniu narzędzia **Pomiń** w zacieniowanym kontenerze wyświetlone zostaną wszystkie elementy, które zostały pominięte. Następnie można wprowadzić je ponownie do kolejki kart.
- Użyj narzędzia **Edytuj**, aby oznaczyć element jako edytowalny lub nieedytowalny. Po wybraniu narzędzia **Edycja** w zacieniowanym kontenerze wyświetlone zostaną wszystkie elementy, których obecnie nie można edytować. Następnie można znowu umożliwić ich edycję. Należy zwrócić uwagę, że niektóre pola są wymagane i nie można ich oznaczyć jako nie do edycji. Obok tych pól widać symbol kłódki.
- Użyj przycisku **Wstaw**, aby wyświetlić listę elementów, które można wstawić na stronie.

    - W obszarze **Wstaw** wybierz narzędzie **Pole**, aby dodać pole do strony. Przy użyciu narzędzia **Pola** można dodawać tylko te pola, które są częścią definicji strony, ale nie są aktualnie na niej wyświetlone. Aby uzyskać informacje o tworzeniu nowych pól, które nie są częścią bieżącej definicji strony, zobacz [Pola niestandardowe](user-defined-fields.md). Po wybraniu narzędzia **Pole** należy najpierw zaznaczyć grupę lub obszar, gdzie chcesz dodać pole. W oknie dialogowym zostanie wyświetlona lista pól powiązanych z wybraną grupą lub obszarem. W oknie dialogowym zaznacz jedno lub więcej pól, które mają zostać dodane, a następnie kliknij opcję **Wstaw**. Aby usunąć pole, które zostało wcześniej dodane, należy powtórzyć proces, ale należy usunąć zaznaczenie tego pola w oknie dialogowym.
    - W obszarze **Wstaw** wybierz narzędzie **PowerApp**, aby na stronie osadzić aplikację utworzoną przy użyciu usługi Microsoft PowerApps. Aby uzyskać szczegółowe informacje o osadzaniu aplikacji usługi PowerApps w stronie, zobacz [Osadzanie aplikacji PowerApp](embed-power-apps.md).

- Wybierz przycisk **Zarządzaj**, aby wyświetlić listę opcji zarządzania związanych ze wszystkimi personalizacjami na bieżącej stronie.

    - Wybierz opcję **Wyczyść**, aby zresetować stronę do domyślnego stanu poinstalacyjnego. Wszystkie personalizacje na bieżącej stronie zostaną usunięte. Nie ma akcji Cofnij. Dlatego użyj tej opcji tylko wtedy, jeśli masz pewność, że chcesz zresetować stronę.
    - Wybierz opcję **Import**, aby wczytać personalizację z pliku utworzonego wcześniej dla tej strony przez siebie lub inną osobę. Wszystkie bieżące personalizacje strony są zastępowane personalizacjami z wybranego pliku.
    - Wybierz opcję **Eksport**, aby zapisać swoje personalizacje strony do pliku. Personalizacje można udostępniać innym użytkownikom. Użytkownicy muszą zaimportować plik zawierający Twoje dane personalizacji strony.

- Wybierz przycisk **Zamknij**, aby zamknąć pasek narzędzi **Personalizacja** i przywrócić pierwotny interaktywny stan strony.

Gdy używany jest pasek narzędzi **Personalizacja**, operacje zapisywania są domyślne. Personalizacje użytkownika zaczynają działać od razu po ich wprowadzeniu, więc nie trzeba naciskać przycisku **Zapisz**. W niektórych przypadkach po wybraniu narzędzia obok elementu pojawia się ikona kłódki. Ten symbol wskazuje, że nie można zmodyfikować właściwości elementu, które są związane z wybranym narzędziem, ponieważ zmiany tych właściwości uniemożliwią poprawne działanie strony.

### <a name="adding-a-tile-list-or-link-to-a-workspace"></a>Dodawanie kafelka, listy lub łącza do obszaru roboczego

W przypadku niektórych stron zawierających listy jest dostępna dodatkowa funkcja personalizacji. Przycisk **Dodaj do obszaru roboczego** w grupie **Personalizacja** na karcie **Opcje** w okienku akcji służy do wyświetlania informacji z bieżącej listy w określonym obszarze roboczym. W obszarze roboczym można wyświetlić widok domyślny lub przefiltrowany i posortowany widok informacji. Można również określić, czy informacje mają być wyświetlane w obszarze roboczym w postaci listy, jako kafelek z podsumowaniem podającym liczbę przedmiotów na liście czy jako link.

[![Dodaj do obszaru roboczego](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Aby dodać listę do obszaru roboczego, najpierw należy prze sortować lub przefiltrować listę na stronie, tak aby informacje były wyświetlane tak, jak mają być widoczne w obszarze roboczym. Następnie wybierz opcję **Dodaj do obszaru roboczego**. Wybierz obszar roboczy, a następnie w polu **Prezentacja** wybierz opcję **Lista**. Po naciśnięciu przycisku **Konfiguruj** pojawi się okno dialogowe, w którym można wybrać kolumny, jakie mają być wyświetlane na liście w obszarze roboczym. Także można wybrać etykietę dla listy w obszarze roboczym.
- Aby dodać kafelek do obszaru roboczego, najpierw przefiltruj listę, tak aby przedstawiała dane, które mają być podsumowane lub chcesz mieć do nich szybki dostęp. Następnie wybierz opcję **Dodaj do obszaru roboczego**. Wybierz obszar roboczy, a następnie w polu **Prezentacja** wybierz opcję **Kafelek**. Po naciśnięciu przycisku **Konfiguruj** pojawi się okno dialogowe, gdzie można określić etykietę, która ma być używana kafelka w obszarze roboczym. Można również określić, czy na kafelku ma się pojawić liczba elementów. Po dodaniu kafelka do obszaru roboczego można go nacisnąć, aby zostanie otwarta bieżąca strona z obszaru roboczego i wyświetlona wyfiltrowana lista skojarzona z kafelkiem.
- Aby dodać łącze do obszaru roboczego, najpierw należy przefiltrować listę na stronie tak, aby pokazywała interesujące Cię dane. Następnie wybierz opcję **Dodaj do obszaru roboczego**. Wybierz obszar roboczy, a następnie w polu **Prezentacja** wybierz opcję **Łącze**. Po naciśnięciu przycisku **Konfiguruj** pojawi się okno dialogowe, gdzie można określić etykietę, która ma być używana dla łącza. Można też opcjonalnie dodać do nowej sekcji etykietę zawierającą ten link.

Po dodaniu listy, kafelka lub łącza do obszaru roboczego można otworzyć ten obszar roboczy i dowolnie zmienić w nim kolejność elementów.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Dodawanie podsumowania z obszaru roboczego do pulpitu nawigacyjnego

Niektóre obszary robocze zawierają kafelki z liczbami i często je również warto umieścić na pulpicie nawigacyjnym. W obszarze roboczym kliknij kafelek z liczbą prawym przyciskiem myszy i wybierz opcję **Personalizuj**. Następnie w oknie właściwości kafelka wybierz opcję **Przypnij do pulpitu nawigacyjnego**. Następnym razem, kiedy otworzysz wybrany pulpit nawigacyjnego (i odświeżysz go), ta liczba zostanie wyświetlona poniżej kafelka nawigacji dla tego obszaru roboczego. Można wybrać tę liczbę, aby przejść bezpośrednio do danych, które reprezentuje.

### <a name="personalizing-your-dashboard"></a>Personalizowanie pulpitu nawigacyjnego

Pulpit nawigacyjny jest często pierwszą stroną, którą widzisz po uruchomieniu programu Finance and Operations. Pulpit nawigacyjny można dostosować, tak aby pokazywane w nim były tylko potrzebne kafelki obszaru roboczego. Ponadto można zmienić kolejność kafelków w dowolny pożądany sposób, zmienić nazwy kafelków nawigacji obszaru roboczego lub dodać całkowicie nowy kafelek do obszaru roboczego.

Aby spersonalizować pulpit nawigacyjny, kliknij prawym przyciskiem myszy dowolny kafelek, a następnie wybierz **Personalizacja**, aby otworzyć okno właściwości kafelka.

- Jeśli chcesz ukryć wybrany kafelek lub zmienić jego nazwę, można dokonać tej zmiany bezpośrednio w oknie właściwości.
- Aby zapisać kafelki obszaru roboczego, wybierz opcję **Personalizuj ten formularz** w oknie właściwości, aby wyświetlić pasek narzędzi **Personalizacji**. Następnie można uporządkować dowolnie kafelki za pomocą narzędzia **Przenieś**.
- Aby utworzyć nowy kafelek obszaru roboczego, w oknie właściwości zaznacz **Dodaj obszar roboczy**. W dolnej części pulpitu nawigacyjnego jest tworzony nowy kafelek obszaru roboczego. Ten kafelek obszaru roboczego można zmieniać dowolnie. Można również dodać listy, kafelki oraz linki do obszaru roboczego w sposób opisany w sekcji tego tematu pt. [Dodawanie list, kafelków lub linków do obszarów roboczych](personalize-user-experience.md#adding-a-tile-list-or-link-to-a-workspace).

## <a name="administration-of-personalization"></a>Administrowanie personalizacją.

Po spersonalizowaniu strony można udostępnić te personalizacje innym użytkownikom poprzez wyeksportowanie spersonalizowanej strony. Następnie możesz poprosić innych użytkowników, aby otworzyli spersonalizowaną stronę i zaimportowali utworzony przez Ciebie plik personalizacji. Alternatywnie można przekazać swoją personalizację użytkownikowi posiadającemu uprawnienia administratora. Ten użytkownik może następnie zastosować Twój plik personalizacji do wielu użytkowników w tym samym czasie.

Użytkownicy posiadający uprawnienia administratora mogą też zarządzać personalizacjami dla innych użytkowników na stronie **Personalizacja**. Ta strona zawiera cztery karty:

- **Zastosuj** — ta opcja pozwala zaimportować lub wybrać personalizację dla co najmniej jednego użytkownika. Aby zastosować personalizację dla jednego lub kilku użytkowników, należy najpierw zaznaczyć rolę i użytkowników, którzy pełnią tę rolę. Następnie wybierz istniejącą personalizację do zastosowania do wybranych użytkowników lub zaimportuj plik personalizacji. Personalizacja jest zweryfikowana i zostanie zastosowana do wszystkich zaznaczonych użytkowników następnym razem, gdy otworzą wybraną stronę.
- **Wyczyść** — Tutaj można wyczyścić wszystkie personalizacje strony lub obszaru roboczego dla jednego lub więcej użytkowników. Najpierw wybierz stronę lub obszar roboczy, aby wyświetlić listę użytkowników, którzy spersonalizowali tę stronę/obszar. Następnie wybierz użytkowników, dla których chcesz wyczyścić personalizację danej strony lub obszaru roboczego, i wybierz opcję **Wyczyść**. Wszystkie personalizacje zastosowane przez wybranych użytkowników do wybranej strony lub obszaru roboczego zostaną usunięte. Tej operacji nie można cofnąć. Jednak jeśli dla strony lub obszaru roboczego zapisano personalizację, można ją ponownie zaimportować.
- **Menedżer użytkownika** — Wybierz użytkownika, aby wyświetlić listę stron spersonalizowanych przez tę osobę. Następnie można włączyć lub wyłączyć dla wybranego użytkownika możliwość korzystania z personalizacji określonych stron lub całego systemu. Można również zaimportować, wyeksportować lub wyczyścić personalizację dla wybranego użytkownika. Ponadto można zresetować objaśnienia funkcji dla wybranego użytkownika. Po wykonaniu tej akcji każde okno podręczne przedstawiające nową funkcję, które wcześniej zostało odrzucone przez użytkownika, będzie wyświetlane ponownie, gdy użytkownik znów napotka tę funkcję.   
- **System** — ta opcja pozwala tymczasowo wyłączyć wszystkie personalizacje dla wszystkich użytkowników w systemie. W takim przypadku personalizacje są usuwane. Wszystkie strony zostaną przywrócone do swoich stanów domyślnych dla wszystkich użytkowników. W przypadku ponownego włączenia personalizacji wszystkie personalizacje zostaną zastosowane ponownie. Można również trwale usunąć wszystkie personalizacje dla wszystkich użytkowników w systemie. Nie jest możliwe odzyskanie personalizacji, które zostały usunięte. Dlatego przed wykonaniem tego zadania należy koniecznie wyeksportować wszystkie personalizacje, które potem możesz chcieć zaimportować.

## <a name="personalization-of-inventory-dimensions"></a>Personalizacja wymiarów magazynowych

W przypadku personalizowania konfiguracji wymiarów magazynowych na stronie należy wziąć pod uwagę ustawienia utworzone przy użyciu opcji **Wyświetl wymiary**. Na przykład można użyć personalizacji w celu ukrycia kolumny dla wymiaru zapasów Numer partii, ale kolumna pojawi się przy następnym otwarciu strony. To zachowanie występuje, ponieważ ustawienia **Wyświetlanie wymiarów** sterują wyświetlanymi kolumnami wymiaru zapasów.

Ustawienia w sekcji **Wyświetlanie wymiarów** mają zastosowanie do wszystkich stron i zastępują wszelkie spersonalizowane konfiguracje pól wymiarów magazynowych na poszczególnych stronach.

W efekcie w poprzednim przykładzie jeśli nie chcesz wyświetlania kolumny dla wymiaru zapasów Numer partii, musisz wyczyścić ten wymiar w ramach opcji tabeli **Wyświetl wymiary**. Ostatecznie ta zmiana będzie stosowana nie tylko na jednej konkretnej stronie, ale na wszystkich stronach.
