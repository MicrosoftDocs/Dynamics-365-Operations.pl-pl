---
title: "Personalizacja interfejsu użytkownika"
description: "W tym artykule wyjaśniono, jak można spersonalizować Microsoft Dynamics 365 dla operacji."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysUserSetup
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 8965c193839002776b3c61036b23b54625c974a4
ms.lasthandoff: 03/31/2017


---

# <a name="personalize-the-user-experience"></a>Personalizacja interfejsu użytkownika

W tym artykule wyjaśniono, jak można spersonalizować Microsoft Dynamics 365 dla operacji.

Istnieje wiele rodzajów personalizacje w usłudze Microsoft Dynamics 365 dla operacji. Niektóre z nich można wybrać z listy na stronie konfiguracji. Niektóre personalizacje są niejawne, na przykład Dynamics 365 dla operacji przechowuje informacje o szerokości kolumn siatki Jeśli dopasujesz, a stan rozwiniętą/zwiniętą skrócone karty. Inne personalizacje są bezpośrednie. W przypadku personalizacji bezpośrednich należy wprowadzić tryb personalizacji interaktywnej i zmodyfikować widok strony poprzez bezpośrednie zarządzanie sposobem wyświetlania lub działania poszczególnych elementów na danej stronie. 

Wszystkie personalizacje dowolnego typu, który użytkownik tworzy w usłudze Dynamics 365 dla operacji są dla danego użytkownika, niezależnie od przedsiębiorstwa, że użytkownik współdziała z. Zmiany, które użytkownik wprowadza na stronie nie mają wpływu na innych użytkowników w systemie.

## <a name="systemwide-options-for-the-current-user"></a>Systemowe opcje dla bieżącego użytkownika
Na pasku nawigacyjnym znajduje się ikonka koła zębatego. To przycisk menu **Ustawienia**. Po otworzeniu menu **Ustawienia** widać szereg elementów do wyboru. Jeśli wybierzesz **Opcje** zostanie wyświetlona strona **opcji** użytkownika. Na tej stronie są 4 karty opcji: **Wygląd**, **Preferencje**, **Konto**, i **Przepływ pracy**.

-   **Wygląd: **umożliwia wybieranie motywu kolorów i domyślnego rozmiaru elementów na stronach.
-   **Preferencje:** w tym miejscu możesz wybrać ustawienia domyślne zawsze podczas otwierania 365 Dynamics dla operacji, w tym firmy, strony początkowej i domyślny tryb Wyświetl/Edytuj (co określa się, jeśli strony jest zablokowany do oglądania lub otwarty do edycji w każdej chwili można otworzyć). Dostępne są również opcje językowe, strefy czasowej, daty, godziny i formatu liczb. Ponadto strona ta zawiera szereg preferencji różnych, których dostępność i funkcjonalność różni się w zależności od wersji oprogramowania.
-   **Konto: **umożliwia podanie Identyfikatora użytkownika i innych opcji związanych z kontem.
-   **Przepływ pracy: **tutaj można ustawiać opcje związane z przepływem pracy.

## <a name="implicit-personalizations"></a>Personalizacje pośrednie
Personalizacje pośrednie to takie, które wykonuje się po prostu poprzez interakcję z określonymi funkcjami sterowania, które zapamiętują bieżący stan i wygląd wykorzystywanych funkcji. 

**Kolumny w siatce:** można dopasować szerokość kolumny na liście, zaznaczając pasek zmiany rozmiaru znajdujący się po lewej lub po prawej stronie nagłówka kolumny i przesuwanie go do lewej lub do prawej o odpowiednią odległość. Dynamics 365 dla operacji będzie przechowywał szerokość, że chcesz i Pokaż tej kolumny z tego szerokość każdorazowo po otwarciu strony z tej listy. 

**Skrócone karty:** niektóre strony mają rozwijane sekcje nazywane skróconymi kartami. Dynamics 365 dla operacji będzie przechowywać które skrócone karty zostały rozszerzone i zwinięty które skrócone karty. Za każdym razem, gdy wracasz do strony, będą rozwinięte i zwinięte te same karty, które były zwinięte lub rozwinięte, gdy poprzednio była używana dana strona. W tym artykule wyjaśnimy jak zmienić układ sekcji skróconych kart. W niektórych przypadkach zwijanie skróconej może zwiększyć wydajność, ponieważ 365 Dynamics dla operacji nie trzeba pobrać informacji dla tej skróconej aż skróconej karcie jest rozwinięty. 

**Pola informacji:** niektóre strony mają sekcję o nazwie okienko pola informacji. To okienko zawiera informacje tylko do odczytu związane z tematem bieżącej strony. Każda sekcja w okienku pola informacji to pole informacji. Można rozwinąć lub zwinąć pole faktów i 365 Dynamics dla operacji będzie przechowywać swoje preferencje. W niektórych przypadkach zwijanie pola fakt może zwiększyć wydajność, ponieważ 365 Dynamics dla operacji nie trzeba pobrać informacji dla tego pola fakt dopóki pole fakt jest rozwinięty.

## <a name="explicit-personalizations-using-the-personalization-toolbar"></a>Personalizacje bezpośrednie przy użyciu paska narzędzi do personalizacji
Dla każdej osoby i firmy ważne są inne informacje. Możliwość dostosowania sposobu Twoje informacje są sortowane, wzajemnie powiązanych z lub nawet ukryty jest kluczem do 365 Dynamics dla operacji osobistych i wydajną obsługę. 

Personalizacje jawne są te personalizacje wykonujących jawnie z zamiarem, aby zmienić wygląd lub zachowanie elementu lub strony, wybierając menu personalizacji. Jest to najprostszy typ personalizacji jawne, gdzie kliknąć element prawym przyciskiem myszy i wybierz **Personalizacja**. (Należy zauważyć, że nie wszystkie elementy na stronie mogą być personalizowane.) Po wybraniu tej metody personalizacji, pojawi się okno właściwości elementu. 

[![Personalizowanie właściwości elementu](./media/personalization-element-properties.jpg)](./media/personalization-element-properties.jpg) 

Na stronie w ten sposób będziesz personalizować element, jeśli chcesz zmienić etykietę elementu, ukryć go, tak aby nie był widoczny na stronie (to nie powoduje zmiany żadnych danych, po prostu informacje nie będą pokazywane), uwzględnić informacje w sekcji podsumowania skróconej karty (jeśli element jest na skróconej karcie), pominąć pole podczas naciskania klawisza Tab lub zablokować możliwość zmiany danych poprzez oznaczenie ich jako „Nie edytuj”. 

Jeśli chcesz przenieść lub ukryć elementy lub wprowadzić kilka zmian, możesz skorzystać z paska narzędzi Personalizacja, który jest dostępny na stronie właściwości elementów po wybraniu opcji **Personalizuj ten formularz**. Pasek narzędzi personalizacji jest również dostępny w okienku akcji formularza, w obszarze grupy Personalizacja na karcie **Opcje**. Wybierz **Personalizuj ten formularz**, aby wyświetlić pasek narzędzi do personalizacji. 

[![Personalizacja paska narzędzi](./media/personalization-personalizationtoolbar.jpg)](./media/personalization-personalizationtoolbar.jpg)

Personalizacja paska narzędzi ma szereg czynności personalizacji. Wybierz narzędzie **Zaznaczanie**, jeśli chcesz zaznaczyć i zmienić właściwości wielu elementów po kolei. Najpierw kliknij narzędzie do zaznaczania, a następnie element, którego właściwości chcesz zmienić. Po zaznaczeniu elementu zostanie wyświetlone okno jego właściwości, w którym można zmienić dowolne właściwości. Można powtórzyć ten proces dla innych elementów w formularzu, które można personalizować. W niektórych przypadkach po zaznaczeniu elementu zobaczysz, że niektórych jego właściwości nie można modyfikować. Oznacza to, że oparte na sposób bieżący element jest używany, Dynamics 365 dla operacji nie można zmienić tej właściwości. Nie można na przykład ukryć pola, które jest wymagane. 

Wybierz narzędzie **Przenieś**, jeśli chcesz zaznaczyć i przenieść element w inne miejsce w bieżącej grupie elementów. (Nie można przenieść elementu poza jego grupę nadrzędną). Najpierw kliknij narzędzie do przenoszenia, a następnie element, który chcesz przenieść. Po kliknięciu elementu, który chcesz przenieść, Dynamics 365 dla operacji skanuje formularz, aby zrozumieć, gdzie ten element można przenosić i utworzyć serię "strefy upuszczania", który wyświetlane jako kolorowe, pogrubione linii obok obszaru, w którym można upuszczać elementu podczas przeciągania elementu wokół w obrębie bieżącej grupy. 

Wybierz narzędzie **Ukryj**, aby wybrać i ukryć element. Aby ukryć element, po prostu wybierz narzędzie Ukryj i kliknij element, który chcesz ukryć. Po wybraniu narzędzia Ukryj wszystkie obecnie ukryte elementy będą widoczne i oznaczone jako zacieniony kontener. Możesz następnie wybrać element, który będzie wyświetlany. Wybierz narzędzie Zaznaczanie, aby sprawdzić wygląd strony z ukrytym zaznaczonym elementem. Wybierz narzędzie **Podsumowanie**, jeśli chcesz, żeby w obszarze podsumowania skróconej karty było widoczne pole numeryczne lub pole ciągu. Narzędzie podsumowania będzie miało zastosowanie tylko do pól zawartych w sekcji skróconej karty. Gdy wybierzesz narzędzie podsumowania, 365 Dynamics dla operacji zostanie wyświetlone wszystkich pól, które zostały wybrane jako pola podsumowania ujęte w kontenerze zacieniowane. Klikając pola, można je interaktywnie dodawać lub usuwać w podsumowaniu skróconej karty. 

Wybierz **Pomiń** narzędzie, aby usunąć element z kolejno kartę strony klawiatury. Po wybraniu narzędzia Pomiń wszystkie aktualnie pominięte elementy będą wyświetlane w cieniowania kontenera tak, że można je ponownie, aby je wybrać część kolejno kartę, wybierając element pominięto. 

Wybierz narzędzie **Edytuj**, aby oznaczyć element jako edytowalny lub nieedytowalny. Po wybraniu narzędzia Edytuj wszystkie obecnie nieedytowalne elementy będą widoczne i oznaczone jako zacieniony kontener. Możesz następnie wybrać element, w którym włączysz możliwość edycji. Uwaga: niektóre pola są wymagane i nie można ich oznaczyć jako nie do edycji. Obok takich pól będzie wyświetlana ikona kłódki. 

Wybierz narzędzie **Dodaj**, aby dodać pole do strony. Za pomocą narzędzia Dodaj nie można utworzyć nowego pola; można natomiast dodawać pola, które są częścią definicji bieżącej strony pole, ale nie są widoczne na tej stronie. Po wybraniu narzędzia Dodaj musisz najpierw wybrać grupę lub obszar, w którym chcesz dodać pole. W oknie dialogowym zostanie wyświetlona lista pól powiązanych z wybraną sekcją. W tym oknie dialogowym można wybrać jedno lub więcej pól i kliknąć opcję Wstaw. Jeśli chcesz usunąć wcześniej dodane pole, powtórz tę procedurę, usuwając zaznaczenie wcześniej dodanego pola. 

Wybierz **zarządzanie** przycisk, aby wyświetlić listę opcji zarządzania związane z wszystkie personalizacje dla bieżącej strony. 

Wybierz **jasne** Aby zresetować stronę na domyolny, zainstalowane Państwo. Zostaną usunięte wszystkie personalizacje na bieżącej stronie. Nie ma żadnej akcji cofania, więc tylko Użyj tej opcji, gdy masz pewność, że chcesz zresetować stronę. 

Wybierz **Importuj**, aby użyć personalizacji z pliku personalizacji utworzonego wcześniej dla tej strony. Zaimportowanie personalizacji spowoduje wyczyszczenie wszystkich zmian personalizacyjnych wprowadzonych na całej stronie i zastosowanie wszystkich ustawień personalizacji z wybranego pliku. Jeśli chcesz zapisać lub udostępnić ustawienia personalizacji, wybierz opcję **Eksportuj**. Spowoduje to zapisanie personalizacji w pliku. 

Wybierz przycisk **Zamknij**, aby zamknąć pasek narzędzi i przywrócić stronę do wcześniejszego stanu interaktywnego. 

Zmiany wprowadzane przy użyciu paska narzędzi Personalizacja są domyślne. Ustawienia personalizacji są aktywne natychmiast po ich wprowadzeniu i nie trzeba klikać przycisku **Zapisz**. W niektórych przypadkach zobaczysz ikonę kłódki obok elementu po zaznaczeniu narzędzia. Oznacza to, że aby strona działała jako poprawnie, nie można modyfikować właściwości powiązanych z wybranego narzędzia. Po otwarciu paska narzędzi personalizacji stronę przestaje być interaktywna. Nie można wprowadzać danych, ani zwijać lub rozwijać sekcji.

## <a name="explicit-personalization-adding-a-tile-or-list-to-a-workspace"></a>Personalizacja bezpośrednia: dodawanie kafelka lub listy do obszaru roboczego
Niektóre strony z listami będą miały dodatkową funkcję personalizacji dostępną w okienku akcji w grupie personalizacji na karcie opcji. Wybierz **Dodaj do obszaru roboczego**, aby wyświetlić listę rozwijaną, która umożliwia pokazywanie informacji na bieżącej liście (filtrowanych, sortowanych lub domyślnie) w obszarze roboczym w formie listy lub kafelka podsumowania (kafelek może pokazywać liczbę elementów na liście). 

[![Add to workspace](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png) 

Aby dodać listę do obszaru roboczego, najpierw należy posortować lub przefiltrować listę, tak aby miała postać, jaką chcesz widzieć w obszarze roboczym, a następnie otwórz okno dialogowe Dodaj do obszaru roboczego. Następnie wybierz żądany obszar roboczy i wybierz **Lista** z listy rozwijanej Prezentacja. Po wybraniu opcji **listy** zostanie wyświetlone okno dialogowe umożliwiające pobranie kolumn, które mają być widoczne na liście, i etykieta listy widocznej w obszarze roboczym. 

Aby dodać kafelek do obszaru roboczego, najpierw przefiltruj listę, tak aby przedstawiała dane, których podsumowanie chcesz widzieć (lub chcesz mieć do niego szybki dostęp). Następnie otwórz okno dialogowe upuszczania Dodaj do obszaru roboczego. Następnie wybierz żądany obszar roboczy i wybierz **Lista** z listy rozwijanej Prezentacja. Po wybraniu opcji **kafelka**, wyświetlone zostanie okno dialogowe umożliwiające podanie etykiety kafelka i określenie, czy ma on pokazywać liczbę. Po umieszczeniu kafelka w obszarze roboczym, kafelek umożliwi otworzenie bieżącej strony z obszaru roboczego i wyświetlenie listy informacji związanych z tym kafelkiem. 

Po dodaniu do obszaru roboczego listy lub kafelka można otworzyć dany obszar roboczy i ponownie zmienić ułożenie listy lub kafelka w grupie, w której te elementy zostały umieszczone.

## <a name="explicit-personalization-adding-a-summary-from-a-workspace-to-a-dashboard"></a>Personalizacja bezpośrednia: dodawanie podsumowania z obszaru roboczego do pulpitu nawigacyjnego
Niektóre obszary robocze zawierają płytek count (płytki z numerami), które również chcesz wyświetlić na pulpicie nawigacyjnym. W obszarze roboczym, kliknij prawym przyciskiem myszy tabliczkę liczby i wybierz **Personalizacja**. Wybierz **Przypnij do pulpitu nawigacyjnego**. Następnym razem, kiedy przejdziesz do wybranego pulpitu nawigacyjnego (i odświeżysz go), zobaczysz tę liczbę poniżej kafelka nawigacji obszaru roboczego na pulpicie nawigacyjnym.

## <a name="explicit-personalization-personalizing-your-dashboard"></a>Personalizacja bezpośrednia: personalizowanie pulpitu nawigacyjnego
Pulpit nawigacyjny jest często pierwszą stronę, którą pojawi się po otwarciu 365 Dynamics dla operacji. Możesz spersonalizować pulpit nawigacyjny i zmienić nazwę kafelków nawigacyjnych obszaru roboczego, aby wyświetlić tylko te kafelki, które chcesz widzieć, zmieniać ich nazwy lub układ. Aby spersonalizować pulpit nawigacyjny, wybierz dowolny kafelek i kliknij prawym przyciskiem myszy, aby otworzyć menu kontekstowe. W menu kontekstowym wybierz **Personalizuj**. Jeśli chcesz ukryć, zmienić nazwę lub pominąć wybrany kafelek, możesz wprowadzić żądane zmiany bezpośrednio w wyświetlonym oknie Właściwości. Jeśli chcesz rozmieścić kafelki, wybierz opcję **Personalizuj ten formularz** w oknie właściwości, aby wyświetlić pasek narzędzi personalizacji. Można następnie użyć narzędzia przenoszenia do uporządkowania kafelków.

## <a name="administration-of-personalization"></a>Administrowanie personalizacją.
Istnieje możliwość personalizowania strony i udostępnienia jej innym użytkownikom. W tym celu wystarczy wyeksportować spersonalizowaną stronę i poprosić innych użytkowników, aby do niej przeszli i zaimportowali utworzony przez Ciebie plik personalizacji. Jeśli użytkownik ma uprawnienia administratora, można też zarządzać personalizacją dla innych użytkowników na stronie **ustawienia personalizacji**. Przejdź do strony b. Na stronie **Personalizacja** znajdują się dwie karty: **System** i ** Użytkownicy**. 

**System:** tutaj można tymczasowo wyłączyć wszelkie opcje personalizacji w systemie. Nie powoduje to usunięcia personalizacji, ale zresetuje wszystkie formularze do stanu domyślnego. Później można ponownie włączyć personalizację i przywrócić wszystkie opcje personalizacji we wszystkich formularzach. Można także usunąć wszystkie ustawienia personalizacji wszystkich użytkowników. Należy pamiętać, że w przypadku usunięcia personalizacji nie można ich później automatycznie ponownie włączyć. Dlatego przed wykonaniem tej czynności, należy pamiętać o wyeksportowaniu wszystkich spersonalizowanych ustawień, tak aby można było je w razie potrzeby zaimportować. 

**Użytkownicy:** tutaj można ustawić dla każdego użytkownika możliwość wprowadzania personalizacji bezpośredniej lub pośredniej. Można także określić, czy użytkownik może wykonywać bezpośrednią lub pośrednią personalizację na określonych formularzach. Można też importować, eksportować lub usunąć personalizację każdego z użytkowników. 

**Uwaga:** w wersji początkowej administracja personalizacją umożliwia zarządzanie tylko użytkownikiem przez użytkownika.


