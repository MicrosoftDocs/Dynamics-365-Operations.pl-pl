---
title: Konfigurowanie zarządzania ofertami
description: W tym temacie opisano sposób konfigurowania zarządzania ofertami w Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 706766ba5133af03d00df99dba1c2a7b0405cd86
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010851"
---
# <a name="set-up-offer-management"></a>Konfigurowanie zarządzania ofertami 

[!include [banner](includes/banner.md)]

Gdy kandydat jest przenoszony do etapu oferty w Dynamics 365 Talent: Attract, trzeba mieć możliwość szybkiego tworzenia ofert dla kandydata, ich niezbędnego zatwierdzania i wysyłania do kandydata. Ponieważ większość ofert jest standardowych, można je tworzyć na podstawie szablonów wielokrotnego użytku. W aplikacji Attract wszystkie oferty są łączone w pakiet oferty, który jest kolekcją jednego lub większej dokumentów oferty. 

Ten temat zawiera listę wszystkich czynności, jakie powinien wykonać administrator aplikacji Attract w celu skonfigurowania różnych szablonów pakietów ofert w ramach funkcji zarządzania ofertami w aplikacji Attract. Użytkownicy nieposiadający ról administratorów nie mają dostępu do tych funkcji.

>[!NOTE]
> Funkcje zarządzania ofertami są dostępne w ramach dodatku kompleksowej obsługi rekrutacji.

## <a name="offer-data"></a>Dane oferty 

Dane oferty to najmniejsza jednostka wewnątrz szablonu pakietu oferty. Typowa oferta składa się z tekstu standardowego i zestawu wartości. Zestawy wartości to jedyne elementy, które mogą się zmieniać między ofertami. Podczas tworzenia oferty najważniejszym aspektem, na którym może się skoncentrować twórca oferty, jest lista symboli zastępczych danych oferty znajdujących się w szablonie pakietu oferty. Aby skonfigurować dane oferty, wykonaj następujące czynności.

1.  Przejdź do okna **Zarządzanie ofertami**.

1.  Rozwiń sekcję **Biblioteka** w lewym okienku nawigacji, a następnie przejdź do strony **Dane oferty**.

    >[!NOTE]
    > Na stronie **Dane oferty** znajdują się sekcje **Szczegóły kandydata** i **Szczegóły funkcji**. Aplikacja Attract oferuje kilka gotowych symboli zastępczych danych oferty.
    
    > Na stronie znajdują się sekcje porządkujące różne symbole zastępcze danych oferty w logiczne grupy. Te sekcje mogą pomóc zarządzać danymi oferty i wprowadzać dane podczas tworzenia oferty.

1.  Aby utworzyć nową sekcję danych oferty, kliknij opcję **Dodaj sekcję** i nadaj sekcji unikatową nazwę.

1.  Aby dodać symbole zastępcze danych oferty do dowolnej sekcji, kliknij przycisk **Dodaj dane oferty** i nadaj unikatową nazwę symbolowi zastępczemu.

1.  Aby zmienić nazwę dowolnej sekcji, umieść wskaźnik myszy nad nazwą sekcji i zaktualizuj nazwę.

1.  Aby edytować nazwę dowolnego istniejącego symbolu zastępczego danych oferty, najpierw upewnij się, że symbol zastępczy nie jest częścią żadnego szablonu. Następnie umieść wskaźnik myszy nad nazwą symbolu zastępczego danych oferty i zaktualizuj nazwę stosownie do potrzeb.

1. Aby usunąć nazwę istniejącego symbolu zastępczego danych oferty, najpierw upewnij się, że symbol zastępczy nie jest częścią żadnego innego szablonu. Następnie umieść wskaźnik myszy nad symbolem zastępczym, a po wyświetleniu ikony kosza kliknij ją. Wtedy symbol zastępczy danych oferty zostanie usunięty.
    >[!NOTE]
    > Wskaźnik liczbowy obok każdego elementu danych oferty pokazuje, w ilu szablonach jest używany symbol zastępczy danych oferty. 

1. Aby usunąć którąkolwiek sekcji, umieść wskaźnik myszy nad jej nazwą. Jeśli żaden symbol zastępczy danych oferty wewnątrz sekcji nie występuje w żadnym szablonie, można kliknąć ikonę kosza, aby usunąć sekcję. 
    >[!NOTE]
    > Usunięcie sekcji spowoduje również usunięcie wszystkich symboli zastępczych danych oferty znajdujących się w tej sekcji.

Po skonfigurowaniu symboli zastępczych danych oferty można ich używać we wszystkich szablonach dokumentów. Symbole zastępcze danych oferty nie są ograniczone do określonego szablonu — tego samego zestawu można używać we wszystkich szablonach.

## <a name="offer-data-rules"></a>Reguły danych oferty

Większość organizacji ma reguły określające sposób tworzenia ofert. Na przykład organizacja może wymagać, aby oferta maksymalnego rocznego wynagrodzenia dla określonej kombinacji lokalizacji i poziomu stażu pracy mieściła się w pewnym zakresie albo żeby poziom oferty dla nowo zatrudnianej osoby mógł przybierać tylko klika ściśle określonych wartości. Obecnie aplikacja Attract obsługuje wszystkie reguły danych za pomocą pliku CSV.

Aby przygotować plik CSV reguł danych, należy wykonać następujące czynności.

1.  Ustal symbol zastępczy danych oferty dla zestawu reguł. Na przykład **Wynagrodzenie roczne**.

1.  Zidentyfikuj zależne wartości symbolu zastępczego danych oferty. Na przykład **Lokalizacja funkcji** i **Poziom**.

1.  Nazwij kolumny 1 i 2 **Lokalizacja funkcji** i **Poziom**.

1.  Aby przekazać zakres wartości, zatytułuj kolumny 3 i 4 **Wynagrodzenie roczne**. Aby przekazywać tylko określoną wartość zamiast zakresu, nazwij tylko kolumnę 3 **Wynagrodzenie roczne**.

1.  Wypełnij pliku programu Microsoft Excel zgodnie z wymaganymi rolami.

1.  Upewnij się, że każdy wiersz zawiera unikatową kombinację wszystkich wartości.

1.  Zapisz plik w formacie CSV.

Aby przekazać plik reguł danych oferty, należy wykonać następujące czynności.

1.  Przejdź do okna **Zarządzanie ofertami**.

1.  Rozwiń sekcję **Biblioteka** w lewym panelu nawigacji, a następnie przejdź do strony **Reguły danych oferty**.

1.  Kliknij przycisk **Nowy zestaw danych**, aby wyświetlić okno dialogowe **Przekaż**.

1.  Nadaj unikatową nazwę zestawowi reguł, a następnie przekaż zapisany plik CSV.

1.  Kliknij przycisk **Dodaj**.
    Zestaw reguł będzie przetwarzany w tle, a po zakończeniu przetwarzania otrzymasz powiadomienie w aplikacji i pocztą e-mail.

    Otrzymasz powiadomienie, jeśli wystąpią błędy w trakcie przetwarzania przekazanego pliku. Wtedy możesz pobrać dziennik błędów, naprawić plik i przekazać go ponownie.

1.  Użyj przycisku wielokropka (**...**), jeśli chcesz pobrać zestaw reguł i zaktualizować zestaw wartości. Po aktualizacji możesz ponownie przekazać plik.

1.  Można usunąć istniejący przekazany zestaw reguł, jeśli definiowany symbol zastępczy nie jest używany w innym szablonie dokumentu.

>[!NOTE]
> - Pod każdym symbolem zastępczym można umieścić tylko jeden unikatowy zestaw kolumn, od których zależy symbol. Na przykład jeśli symbol zastępczy **Wynagrodzenie roczne** zależy od kolumn **Lokalizacja funkcji** i **Poziom**, nie można przekazać innego zestawu reguł, w którym symbol zastępczy **Wynagrodzenie roczne** zależy od innego zestawu kolumn.

> - Przykładowe zestawy reguł danych oferty można pobierać na karcie **Przykłady** na stronie **Reguły danych oferty**.

> - Gdy twórca oferty zastąpi wartości zalecane przez reguły danych oferty, oferta jest oznaczana jako niestandardowa i wtedy zostanie wymuszony przepływu pracy zatwierdzania oferty.

## <a name="document-templates"></a>Szablony dokumentów

Szablon dokumentu oferty może pomóc administratorom tworzyć listy z ofertą. Szablon dokumentu oferty jest kombinacją tekstu, który będzie częścią oferty, i zdefiniowanych symboli zastępczych danych oferty. 

Aby utworzyć szablon dokumentu oferty, wykonaj następujące czynności.

1.  Przejdź do okna **Zarządzanie ofertami**.

1.  Rozwiń sekcję **Biblioteka** w lewym okienku nawigacji, a następnie przejdź do strony **Szablony**.

    Strona **Szablony** zawiera listę szablonów dokumentów, które zostały już zdefiniowane.

1.  Aby utworzyć nowy szablon dokumentu, kliknij przycisk **Nowy szablon**.

1.  Nadaj szablonowi unikatową nazwę i kliknij przycisk **Utwórz**.

1.  Za pomocą edytora tekstu sformatowanego wstaw lub zmodyfikuj zawartość dokumentu oferty. Możesz wstawić tabele, obrazy i hiperłącza, korzystając z opcji dostępnych w górnej części edytora tekstu.

1.  Symbole zastępcze danych oferty można wstawić w dokumencie szablonu oferty następującymi metodami:

    - Przeciągnięcie z prawego okienka i upuszczenie.

    - Umieszczenie hasztagu symbolu zastępczego danych oferty bezpośrednio w odpowiednim miejscu. Wpisz znak **\#**, a następnie rozpocznij wpisywanie nazwy symbolu zastępczego danych oferty. Pojawi się lista rozwijana z opcjami. Kliknij opcję lub naciśnij klawisz **Enter**, aby wstawić symbol zastępczy danych oferty.

    >[!NOTE]
    > - Aby skojarzyć symbol zastępczy z szablonem dokumentu oferty bez pokazywania wartości symbolu kandydatowi, umieść wskaźnik myszy nad symbolem zastępczym danych oferty i kliknij ikonę **Przypnij**. Spowoduje to przesunięcie symbolu zastępczego do sekcji **Przypięte dane oferty** w szablonie dokumentu oferty. Aby odpiąć, wykonaj te same czynności, ale na liście symboli zastępczych danych oferty kliknij pozycję **Odepnij**.

    > - Aby wyświetlić listę aktywnych symboli zastępczych danych oferty, przejdź do karty **Aktywne** w prawym okienku.

    > - Jeśli wstawisz symbol zastępczy sterowany przez zestaw reguł danych oferty, możesz obejrzeć zależność tego symbolu zastępczego danych oferty od innych wartości.

    > - Alternatywnie możesz **zaimportować** zawartość z pliku .docx na lokalnym komputerze i edytować ją zgodnie z wymaganiami. Dzięki temu nie trzeba wpisywać całej zawartości w edytorze.

1. Aby wyświetlić podgląd dokumentu oferty, użyj opcji **Podgląd** w górnej części strony.

1. Aby określić, czy twórca oferty może edytować zawartość dokumentu oferty, użyj opcji **Zarządzaj uprawnieniami** w górnej części strony. Jeśli chcesz, aby twórca oferty mógł tylko wstawiać wartości symboli zastępczych, a nie edytować tekst, ustaw wartość uprawnienia na **Nie**.

1. Kliknij przycisk **Zapisz**, aby zapisać swoją pracę. Szablon zostanie zapisany w stanie Wersja robocza.

1. Aby sfinalizować dokument i oznaczyć go jako opublikowany, kliknij przycisk **Zakończ**.

1. Możesz zobaczyć, które szablony dokumentów są obecnie aktywne, w trybie roboczym oraz zostały zarchiwizowane i nie są już używane na stronie docelowej biblioteki szablonów dokumentów.

>[!NOTE]
> Można usunąć każdy szablon dokumentu oferty, który nie są częścią istniejącego szablonu pakietu oferty.


## <a name="offer-package-templates"></a>Szablony pakietów ofert

Pakiety ofert to drugie artefakty oferty, które są udostępniane kandydatowi. Składają się z jednego lub kombinacji wielu szablonów dokumentów oferty. Aby utworzyć pakiet oferty, wykonaj następujące czynności.

1.  Przejdź do okna **Zarządzanie ofertami**.

1.  Z lewego okienka nawigacji przejdź do strony **Pakiety**.

    Zostanie wyświetlona lista aktywnych szablonów pakietów, które są dostępne do użytku przez twórców ofert.

1.  Aby utworzyć nowy pakiet oferty, kliknij przycisk **Nowy pakiet**.

1.  Wprowadź unikatową nazwę i kliknij przycisk **Utwórz**.

1.  Kliknij przycisk **Dodaj szablon**.

    >[!NOTE]
    > - Możesz utworzyć nowy szablon albo wybrać jeden z istniejących.

    > - Jeśli postanowisz dodać istniejący szablon, upewnij się, że szablon dokumentu oferty został zapisany, sfinalizowany i oznaczony jako aktywny.
    
    > - Można wybrać dowolną potrzebną liczbę szablonów dokumentów. 
    
1.  Kliknij przycisk **Gotowe**, aby wrócić do okna **Zarządzanie pakietami**.

    Można skonfigurować kolejność dokumentów oraz wskazać, czy określone dokumenty oferty są wymagane podczas tworzenia oferty. Twórca oferty będzie miał możliwość usunięcia dokumentów oznaczonych jako **Niewymagane**.

1. Aby zapisać szablon pakietu oferty, tak aby mogli go używać wszyscy twórcy ofert, kliknij **Zapisz i opublikuj**.

   Aby wyświetlić wersje robocze szablonów pakietów ofert, przejdź do karty **Wersje robocze**. Jeśli w szablonie pakietu oferty zostanie wprowadzona zmiana, należy zapisać szablon i ponownie go opublikować.

## <a name="configure-an-offer-process"></a>Konfigurowanie procesu tworzenia oferty

Istnieje kilka etapów procesu tworzenia oferty, które mogą być konfigurowane przez administratora aplikacji Attract.

- **Zatwierdzenia ofert** — Określ, czy zatwierdzenia ofert są wymagane, zanim ofertę można wysłać do kandydata. Jako administrator możesz również zdecydować, czy wszystkie zatwierdzenia ofert będą następowały kolejno, czy równolegle. Możesz także określić, czy osoby zatwierdzające oferty muszą dodawać komentarze do swoich zatwierdzeń ofert. Zatwierdzenia ofert są obowiązkowe dla wszystkich ofert niestandardowych.

- **Funkcje oferty dla kandydata** — Jako administrator możesz określić, czy wszystkie oferty mają datę ważności, a jeśli tak, ile powinien wynosić domyślny okres ważności oferty. Można również określić, czy kandydaci mają prawo odrzucać oferty.

- **e-podpisy** — jako administrator, można także wybrać metodę używaną przez kandydatów do podpisywania ofert.
    - Adobe Sign — wszystkie pakiety ofert będą wysyłane i podpisywane przez Adobe Sign. Każdy twórca oferty publikujący ofertę musi mieć konto Adobe Sign połączone z Attract. Licencje Adobe Sign i bezpłatna wersja próbna, zobacz ten [link](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).

    - DocuSign — wszystkie pakiety ofert będą wysyłane i podpisywane przez DocuSign. Każdy twórca oferty publikujący ofertę musi mieć konto DocuSign połączone z Attract. 
    
    - ESign — jest to opcja domyślna, dostępna od razu po pierwszym uruchomieniu, zapewniająca użytkownikowi opcję podpisania oferty przez wpisanie imienia i nazwiska oraz inicjałów.


Aby uzyskać więcej informacji o procesie tworzenia oferty, zobacz [Tworzenie, zatwierdzanie i podpisywanie ofert](./creating-offers.md).
