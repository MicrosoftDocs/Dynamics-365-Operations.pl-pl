---
title: "Personalizacja interfejsu użytkownika"
description: "W tym temacie wyjaśniono, jak można spersonalizować program Microsoft Dynamics 365 for Finance and Operations."
author: RobinARH
manager: AnnBe
ms.date: 08/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserSetup
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: cf2ad9f95035aaf004f2da779a8492ff2d91d399
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="personalize-the-user-experience"></a>Personalizacja interfejsu użytkownika

[!include[banner](../includes/banner.md)]


W tym temacie wyjaśniono, jak można spersonalizować program Microsoft Dynamics 365 for Finance and Operations.

Microsoft Dynamics 365 for Finance and Operations daje wiele różnych możliwości dostosowania oprogramowania do własnych potrzeb. Niektóre z nich można wybrać z listy na stronie konfiguracji. Niektóre personalizacje są domyślne. Na przykład Dynamics 365 for Finance and Operations przechowuje informacje o szerokość kolumn siatki, jeśli je zmienisz, oraz o rozwiniętych/zwiniętych skróconych kartach. Inne personalizacje są bezpośrednie. W przypadku personalizacji bezpośrednich należy wprowadzić tryb personalizacji interaktywnej i zmodyfikować widok strony poprzez bezpośrednie zarządzanie sposobem wyświetlania lub działania poszczególnych elementów na danej stronie. 

Wszystkie personalizacje dowolnego typu, które użytkownik wprowadzi w programie Dynamics 365 for Finance and Operations, dotyczą wyłącznie danego użytkownika bez względu na firmę, z którą współpracuje. Zmiany, które użytkownik wprowadza na stronie nie mają wpływu na innych użytkowników w systemie.

## <a name="systemwide-options-for-the-current-user"></a>Opcje dla bieżącego użytkownika dotyczące całego systemu
Na pasku nawigacyjnym znajduje się ikonka koła zębatego. To przycisk menu **Ustawienia**. Po otworzeniu menu **Ustawienia** widać szereg elementów do wyboru. Jeśli wybierzesz **Opcje** zostanie wyświetlona strona **opcji** użytkownika. Na tej stronie są 4 karty opcji: 

-   **Wygląd** — Umożliwia wybieranie motywu kolorów i domyślnego rozmiaru elementów na stronach.
-   **Preferencje** — W tym miejscu można wybrać ustawienia domyślne stosowane przy każdym otwarciu programu Dynamics 365 for Finance and Operations, w tym firmę, stronę początkową i domyślny tryb Wyświetl/Edytuj (określający, czy strona jest zablokowana do wyświetlania lub otwarta do edycji w każdym jej wyświetleniu). Dostępne są również opcje językowe, strefy czasowej, daty, godziny i formatu liczb. Ponadto strona ta zawiera szereg preferencji różnych, których dostępność i funkcjonalność różni się w zależności od wersji oprogramowania.
-   **Konto** — Umożliwia podanie Identyfikatora użytkownika i innych opcji związanych z kontem.
-   **Przepływ pracy** — Tutaj można ustawiać opcje związane z przepływem pracy.

## <a name="implicit-personalizations"></a>Personalizacje pośrednie
Personalizacje pośrednie to takie, które wykonuje się po prostu poprzez interakcję z określonymi funkcjami sterowania, które zapamiętują bieżący stan i wygląd wykorzystywanych funkcji. 

**Kolumny w siatce** — Można dopasować szerokość kolumny na liście, zaznaczając pasek zmiany rozmiaru znajdujący się po lewej lub po prawej stronie nagłówka kolumny i przesuwanie go do lewej lub do prawej o odpowiednią odległość. Program Dynamics 365 for Finance and Operations zapamięta wybraną szerokość i będzie wyświetlał kolumnę o tej szerokości za każdym razem, gdy otworzysz stronę z tą listą. 

**Skrócone karty** — Niektóre strony mają rozwijane sekcje nazywane skróconymi kartami. Program Dynamics 365 for Finance and Operations zapamiętuje, które skrócone karty zostały rozwinięte lub zwinięte. Za każdym razem, gdy wracasz do strony, będą rozwinięte i zwinięte te same karty, które były zwinięte lub rozwinięte, gdy poprzednio była używana dana strona. W tym artykule wyjaśnimy jak zmienić układ sekcji skróconych kart. W niektórych przypadkach zwinięcie skróconej karty może poprawić wydajność, bo program Dynamics 365 for Finance and Operations nie będzie musiał pobierać informacji zawartych w tej karcie, dopóki nie zostanie ona rozwinięta. 

**Pola informacji** — Niektóre strony mają sekcję o nazwie okienko pola informacji. To okienko zawiera informacje tylko do odczytu związane z tematem bieżącej strony. Każda sekcja w okienku pola informacji to pole informacji. Pola informacji można zwijać i rozwijać, a program Dynamics 365 for Finance and Operations zapamiętuje preferencje użytkownika. W niektórych przypadkach zwinięcie pola informacji może poprawić wydajność, bo program Dynamics 365 for Finance and Operations nie będzie musiał pobierać informacji zawartych w tym polu, dopóki nie zostanie ono rozwinięte.

## <a name="explicit-personalizations-using-the-personalization-toolbar"></a>Personalizacje bezpośrednie przy użyciu paska narzędzi do personalizacji
Dla każdej osoby i firmy ważne są inne informacje. Możliwość dostosowania sposobu uporządkowania informacji, interakcji z nimi lub ukrywania danych ma kluczowe znaczenie w kontekście dostosowania programu Dynamics 365 for Finance and Operations do indywidualnych potrzeb. 

Personalizacje bezpośrednie to te, które wykonujesz bezpośrednio z zamiarem zmiany wyglądu lub zachowania danego elementu strony poprzez wybranie opcji z menu personalizacji. Najbardziej podstawowym typem personalizacji bezpośredniej jest kliknięcie elementu prawym przyciskiem myszy i wybranie opcji **Personalizuj**. (Pamiętaj, że nie wszystkie elementy na stronie można personalizować). Po wybraniu tej metody personalizacji pojawi się okno właściwości elementu. 

[![Personalizowanie właściwości elementu](./media/personalization-element-properties.jpg)](./media/personalization-element-properties.jpg) 

Na stronie w ten sposób będziesz personalizować element, jeśli chcesz zmienić etykietę elementu, ukryć go, tak aby nie był widoczny na stronie (to nie powoduje zmiany żadnych danych, po prostu informacje nie będą pokazywane), uwzględnić informacje w sekcji podsumowania skróconej karty (jeśli element jest na skróconej karcie), pominąć pole podczas naciskania klawisza Tab lub zablokować możliwość zmiany danych poprzez oznaczenie ich jako „Nie edytuj”. 

Jeśli chcesz przenieść lub ukryć elementy lub wprowadzić kilka zmian, możesz skorzystać z paska narzędzi Personalizacja, który jest dostępny na stronie właściwości elementów po wybraniu opcji **Personalizuj ten formularz**. Pasek narzędzi Personalizacja jest także dostępny w okienku akcji formularza w grupie Personalizuj karty **Opcje**. Wybierz opcję **Personalizuj ten formularz**, a zobaczysz pasek narzędzi Personalizacja. 

[![Pasek narzędzi do personalizacji](./media/personalization-personalizationtoolbar.jpg)](./media/personalization-personalizationtoolbar.jpg)

Pasek narzędzi do personalizacji zawiera wiele akcji personalizacji. Wybierz narzędzie **Zaznaczanie**, jeśli chcesz zaznaczyć i zmienić właściwości wielu elementów po kolei. Najpierw kliknij narzędzie do zaznaczania, a następnie element, którego właściwości chcesz zmienić. Po zaznaczeniu elementu zostanie wyświetlone okno jego właściwości, w którym można zmienić dowolne właściwości. Można powtórzyć ten proces dla innych elementów w formularzu, które można personalizować. W niektórych przypadkach po zaznaczeniu elementu zobaczysz, że niektórych jego właściwości nie można modyfikować. Oznacza to, że zależne od sposobu używania bieżącego elementu program Finance and Operations nie pozwala na zmianę jego właściwości. Nie można na przykład ukryć pola, które jest wymagane. 

Wybierz narzędzie **Przenieś**, jeśli chcesz zaznaczyć i przenieść element w inne miejsce w bieżącej grupie elementów. (Nie można przenieść elementu poza jego grupę nadrzędną). Najpierw kliknij narzędzie do przenoszenia, a następnie element, który chcesz przenieść. Po kliknięciu elementu, który chcesz przenieść, program Finance and Operations zeskanuje formularz, aby określić miejsca, w których można umieścić dany element, a następnie utworzy serię miejsc upuszczenia widocznych jako kolorowe pogrubione linie obok obszaru, w którym można upuścić element podczas przeciągania go w bieżącej grupie. 

Wybierz narzędzie **Ukryj**, aby wybrać i ukryć element. Aby ukryć element, po prostu wybierz narzędzie Ukryj i kliknij element, który chcesz ukryć. Po wybraniu narzędzia Ukryj wszystkie obecnie ukryte elementy będą widoczne i oznaczone jako zacieniony kontener. Możesz następnie wybrać element, który będzie wyświetlany. Wybierz narzędzie Zaznaczanie, aby sprawdzić wygląd strony z ukrytym zaznaczonym elementem. Wybierz narzędzie **Podsumowanie**, jeśli chcesz, żeby w obszarze podsumowania skróconej karty było widoczne pole numeryczne lub pole ciągu. Narzędzie podsumowania będzie miało zastosowanie tylko do pól zawartych w sekcji skróconej karty. Po wybraniu narzędzia podsumowania program Finance and Operations pokaże wszystkie pola, które zostały wybrane jako pola podsumowania poprzez zamknięcie ich w zacienionym kontenerze. Klikając pola, można je interaktywnie dodawać lub usuwać w podsumowaniu skróconej karty. 

Wybierz narzędzie **Pomiń**, aby usunąć element z sekwencji tabulacji na stronie. Po wybraniu narzędzia Pomiń wszystkie obecnie pominięte elementy będą wyświetlane w zacienionym kontenerze, w którym można je ponownie wybrać i uwzględnić w sekwencji tabulacji. 

Wybierz narzędzie **Edytuj**, aby oznaczyć element jako edytowalny lub nieedytowalny. Po wybraniu narzędzia Edytuj wszystkie obecnie nieedytowalne elementy będą widoczne i oznaczone jako zacieniony kontener. Możesz następnie wybrać element, w którym włączysz możliwość edycji. Uwaga: niektóre pola są wymagane i nie można ich oznaczyć jako nie do edycji. Obok takich pól będzie wyświetlana ikona kłódki. 

Wybierz narzędzie **Dodaj**, aby dodać pole do strony. Za pomocą narzędzia Dodaj nie można utworzyć nowego pola; można natomiast dodawać pola, które są częścią definicji bieżącej strony pole, ale nie są widoczne na tej stronie. Po wybraniu narzędzia Dodaj musisz najpierw wybrać grupę lub obszar, w którym chcesz dodać pole. W oknie dialogowym zostanie wyświetlona lista pól powiązanych z wybraną sekcją. W tym oknie dialogowym można wybrać jedno lub więcej pól i kliknąć opcję Wstaw. Jeśli chcesz usunąć wcześniej dodane pole, powtórz tę procedurę, usuwając zaznaczenie wcześniej dodanego pola. 

Wybierz przycisk **Zarządzaj**, aby wyświetlić listę opcji zarządzania związanych ze wszystkimi personalizacjami na bieżącej stronie. 

Wybierz opcję **Wyczyść**, aby zresetować stronę do domyślnych zainstalowanych ustawień. Zostaną usunięte wszystkie personalizacje na bieżącej stronie. Nie można cofać zmian, dlatego tej opcji należy używać tylko wtedy, gdy na pewno chcesz zresetować stronę. 

Wybierz **Importuj**, aby użyć personalizacji z pliku personalizacji utworzonego wcześniej dla tej strony. Zaimportowanie personalizacji spowoduje wyczyszczenie wszystkich zmian personalizacyjnych wprowadzonych na całej stronie i zastosowanie wszystkich ustawień personalizacji z wybranego pliku. Jeśli chcesz zapisać lub udostępnić ustawienia personalizacji, wybierz opcję **Eksportuj**. Spowoduje to zapisanie personalizacji w pliku. 

Wybierz przycisk **Zamknij**, aby zamknąć pasek narzędzi i przywrócić stronę do wcześniejszego stanu interaktywnego. 

Zmiany wprowadzane przy użyciu paska narzędzi Personalizacja są domyślne. Ustawienia personalizacji są aktywne natychmiast po ich wprowadzeniu i nie trzeba klikać przycisku **Zapisz**. W niektórych przypadkach po wybraniu narzędzia pojawi się obok ikona kłódki. Oznacza to, że w celu zapewnienia prawidłowego działania strony nie można zmieniać właściwości związanych z wybranym narzędziem. Po otwarciu paska narzędzi personalizacji stronę przestaje być interaktywna. Nie można wprowadzać danych, ani zwijać lub rozwijać sekcji.

## <a name="explicit-personalization-adding-a-tile-or-list-to-a-workspace"></a>Personalizacja bezpośrednia: dodawanie kafelka lub listy do obszaru roboczego
Niektóre strony z listami będą zawierały dodatkową funkcję personalizacji dostępną w okienku akcji, w grupie Personalizuj karty Opcje. Wybierz opcję **Dodaj do obszaru roboczego**, aby otworzyć listę rozwijaną umożliwiającą wyświetlenie informacji na bieżącej liście (odfiltrowanej i posortowanej lub domyślnej) w obszarze roboczym w formie listy lub kafelka (można ich użyć do wyświetlenia liczby pozycji na liście). 

[![Dodaj do obszaru roboczego](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png) 

Aby dodać listę do obszaru roboczego, najpierw należy posortować lub przefiltrować listę, tak aby miała postać, jaką chcesz widzieć w obszarze roboczym, a następnie otwórz okno dialogowe Dodaj do obszaru roboczego. Następnie wybierz żądany obszar roboczy i wybierz **Lista** z listy rozwijanej Prezentacja. Po wybraniu opcji **listy** zostanie wyświetlone okno dialogowe umożliwiające pobranie kolumn, które mają być widoczne na liście, i etykieta listy widocznej w obszarze roboczym. 

Aby dodać kafelek do obszaru roboczego, najpierw przefiltruj listę, tak aby przedstawiała dane, których podsumowanie chcesz widzieć (lub chcesz mieć do niego szybki dostęp). Następnie otwórz okno dialogowe upuszczania Dodaj do obszaru roboczego. Następnie wybierz żądany obszar roboczy i wybierz **Lista** z listy rozwijanej Prezentacja. Po wybraniu opcji **kafelka**, wyświetlone zostanie okno dialogowe umożliwiające podanie etykiety kafelka i określenie, czy ma on pokazywać liczbę. Po umieszczeniu kafelka w obszarze roboczym, kafelek umożliwi otworzenie bieżącej strony z obszaru roboczego i wyświetlenie listy informacji związanych z tym kafelkiem. 

Po dodaniu do obszaru roboczego listy lub kafelka można otworzyć dany obszar roboczy i ponownie zmienić ułożenie listy lub kafelka w grupie, w której te elementy zostały umieszczone.

## <a name="explicit-personalization-adding-a-summary-from-a-workspace-to-a-dashboard"></a>Personalizacja bezpośrednia: dodawanie podsumowania z obszaru roboczego do pulpitu nawigacyjnego
Niektóre obszary robocze zawierają kafelki (płytki z liczbami), które mogą być także widoczne w pulpicie nawigacyjnym. W obszarze roboczym kliknij kafelek z liczbą prawym przyciskiem myszy i wybierz opcję **Personalizuj**. Wybierz **Przypnij do pulpitu nawigacyjnego**. Następnym razem, kiedy przejdziesz do wybranego pulpitu nawigacyjnego (i odświeżysz go), zobaczysz tę liczbę poniżej kafelka nawigacji obszaru roboczego na pulpicie nawigacyjnym.

## <a name="explicit-personalization-personalizing-your-dashboard"></a>Personalizacja bezpośrednia: personalizowanie pulpitu nawigacyjnego
Pulpit nawigacyjny jest często pierwszą stroną, którą widzisz po uruchomieniu programu Finance and Operations. Możesz spersonalizować pulpit nawigacyjny i zmienić nazwę kafelków nawigacyjnych obszaru roboczego, aby wyświetlić tylko te kafelki, które chcesz widzieć, zmieniać ich nazwy lub układ. Aby spersonalizować pulpit nawigacyjny, wybierz dowolny kafelek i kliknij prawym przyciskiem myszy, aby otworzyć menu kontekstowe. W menu kontekstowym wybierz **Personalizuj**. Jeśli chcesz ukryć, zmienić nazwę lub pominąć wybrany kafelek, możesz wprowadzić żądane zmiany bezpośrednio w wyświetlonym oknie Właściwości. Jeśli chcesz rozmieścić kafelki, wybierz opcję **Personalizuj ten formularz** w oknie właściwości, aby wyświetlić pasek narzędzi personalizacji. Można następnie użyć narzędzia przenoszenia do uporządkowania kafelków.

## <a name="administration-of-personalization"></a>Administrowanie personalizacją.
Po spersonalizowaniu strony można udostępnić te personalizacje innym użytkownikom poprzez wyeksportowanie strony. Następnie możesz poprosić innych użytkowników, aby przeszli do spersonalizowanej strony i zaimportowali utworzony przez Ciebie plik personalizacji.

Użytkownicy posiadający uprawnienia administratora mogą też zarządzać personalizacjami dla innych użytkowników na stronie **Personalizacja**. Ta strona zawiera cztery karty: 

- **System** — Tutaj można tymczasowo wyłączyć wszystkie personalizacje istniejące w systemie. W takim przypadku nie usuwasz personalizacji. Zamiast tego po prostu resetujesz wszystkie strony do ich stanu domyślnego. Jeśli później ponownie włączysz personalizację, wszystkie personalizacje zostaną ponownie zastosowane do stron użytkownika. Można także usunąć wszystkie ustawienia personalizacji wszystkich użytkowników. Należy pamiętać, że w przypadku usunięcia personalizacji nie można ich później automatycznie ponownie włączyć. Dlatego przed wykonaniem tego kroku należy koniecznie wyeksportować wszystkie personalizacje, które potem możesz chcieć zaimportować.
- **Użytkownicy** — Tutaj można określić, czy każdy użytkownik może dokonywać personalizacji pośredniej, czy bezpośredniej. Można także określić, czy każdy użytkownik może wykonywać bezpośrednią lub pośrednią personalizację na określonych stronach. Można też zaimportować, wyeksportować lub usunąć personalizację każdego z użytkowników.
- **Import** — Tutaj można zaimportować personalizację dla jednego lub więcej użytkowników. Tej karty należy użyć po utworzeniu personalizacji na stronie lub w obszarze roboczym, i następnie jej wyeksportowany jako pliku personalizacji. Aby zaimportować plik personalizacji i go zastosować do jednego lub więcej użytkowników, wybierz poszczególnych użytkowników z listy wszystkich użytkowników lub wyfiltruj według określonej roli, a następnie zaznacz użytkowników mających tę rolę. Po wybraniu użytkowników, którzy będą używać Twojej personalizacji, kliknij przycisk **Import** i zaznacz swój plik personalizacji. Personalizacja zostanie zweryfikowana i zastosowana do wszystkich zaznaczonych użytkowników następnym razem, gdy otworzą wybraną stronę.
- **Wyczyść** — Tutaj można usunąć personalizacje strony lub obszaru roboczego dla jednego lub więcej użytkowników. Najpierw zaznacz stronę lub obszar roboczy, z którego chcesz usunąć personalizacje. Następnie wybierz poszczególnych użytkowników z listy wszystkich użytkowników lub wyfiltruj według określonej roli, a następnie zaznacz użytkowników mających tę rolę. Po wybraniu strony lub obszaru roboczego i użytkowników kliknij przycisk **Wyczyść**. Wszystkie personalizacje zastosowane przez wybranych użytkowników do wybranej strony lub obszaru roboczego zostaną usunięte. Tej operacji nie można cofnąć. Jednak jeśli strona lub obszar roboczy ma zapisaną personalizację, można ponownie zaimportować tę personalizację.

## <a name="personalization-of-inventory-dimensions"></a>Personalizacja wymiarów magazynowych

W przypadku personalizowania konfiguracji wymiarów magazynowych na stronie należy wziąć pod uwagę ustawienia utworzone przy użyciu opcji **Wyświetl wymiary**. Na przykład jeśli używasz personalizacji w celu ukrycia kolumny wymiaru magazynowego Numer partii, a kolumna pojawi się przy następnym otwarciu strony, być może jest to spowodowane tym, że ustawienia wyświetlania wymiarów decydują o wyświetlaniu kolumn wymiarów magazynowych. 

Ustawienia wyświetlania wymiarów mają zastosowanie do wszystkich stron i zastępują wszelkie spersonalizowane konfiguracje pól wymiarów magazynowych na poszczególnych stronach. 

Na przykład wymiar magazynowy Numer partii musiałby zostać wyczyszczony w opcji **Wyświetl wymiary**, jeśli w tabeli ta kolumna nie miałaby być wyświetlana. Ostatecznie ta zmiana byłaby stosowana nie tylko na jednej konkretnej stronie, ale na wszystkich stronach.

