---
title: Ustawienia wyświetlania urządzenia przenośnego używanego w magazynie
description: W tym artykule opisano konfigurowanie wyglądu ekranu urządzenia przenośnego oraz mapowanie skrótów klawiaturowych na formanty takie jak przyciski.
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFColor, WHSRFColorPicker, WHSWorkUserDisplaySettings
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 29071
ms.assetid: 931a02e8-b561-45e3-9c44-06b875ced1b4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16f332da00d2230ecb4cebc526b6456314564e55
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "328040"
---
# <a name="warehouse-mobile-device-display-settings"></a>Ustawienia wyświetlania urządzenia przenośnego używanego w magazynie

[!include [banner](../includes/banner.md)]

W tym artykule opisano konfigurowanie wyglądu ekranu urządzenia przenośnego oraz mapowanie skrótów klawiaturowych na formanty takie jak przyciski. 

Uwaga: Ten artykuł dotyczy funkcji zaawansowanego zarządzania magazynem w module Zarządzanie magazynem. Urządzenia przenośne mogą służyć do wielu zadań wykonywanych przez pracowników magazynu.

## <a name="specify-styles-and-map-keyboard-shortcuts"></a>Określanie stylów i mapowanie skrótów klawiaturowych
W ramach konfiguracji urządzenia przenośnego można zdefiniować różne układy dla urządzeń przenośnych. Aby to zrobić, należy znać nazwę pliku kaskadowe arkusze stylów (CSS) i pliku rozszerzenie aktywnej strony serwera (ASPX). Domyślne pliki są instalowane podczas instalacji portalu urządzeń przenośnych używanych w magazynie. Jeśli nie znasz nazw plików, skontaktuj się z administratorem systemu. Na stronie **Ustawienia wyświetlania urządzenia przenośnego** można zdefiniować nowe style:

-    W **pliku CSS** wprowadź nazwę pliku CSS. Uwzględnij rozszerzenie .css nazwy pliku
-   W polu **Widok ustawień wyświetlania urządzenia przenośnego** określ plik ASPX. **Nie** dodawaj rozszerzenia .aspx nazwy pliku.

Pliki CSS i ASPX muszą znajdować się w określonym katalogu, tak aby aplikacja internetowych usług informacyjnych (IIS) mogła je wczytać. Może to być przydatne do definiowania różnych plików CSS, jeśli uruchamiasz funkcje urządzenia przenośnego w różnych przeglądarkach i na różnych rodzajach sprzętu wymagającego odmiennego sterowania układem. Proste ustawienia, takie jak kolor tła, czcionki i rozmiar czcionki dla tekstu oraz szerokość i zachowanie przycisków, łatwo można kontrolować za pomocą różnych plików CSS. Plik ASPX jest używany do wyświetlania witryny dla urządzeń przenośnych w aplikacji ASP.NET po stronie serwera. Plik określa sposób rozłożenia ogólnej struktury HTML. Tę funkcję należy personalizować tylko wtedy, gdy występują poważne problemy strukturalne z kodem HTML i JavaScript, i trzeba zmienić ten kod pod kątem określonych urządzeń. Aby zmapować formanty HTML na stronie dla urządzenia przenośnego do skrótów klawiaturowych, na stronie **Ustawienia wyświetlania urządzenia przenośnego** w polu **skrótu klawiaturowego** należy przypisać kody numeryczne kluczy. Można użyć menu **Wyświetl kody skrótów klawiaturowych** urządzenia przenośnego, aby znaleźć kody znaku numerycznego. Należy zwrócić uwagę, że mapowania mogą być różne, w zależności od sprzętu, który jest używany. Przed utworzeniem mapowania należy wykorzystać następującą składnię:

&lt;nazwa formantu&gt;(&lt;nazwa klawisza&gt;)=&lt;kod klawisza&gt;;

Poniżej znajdują się wyjaśnienia dotyczące części składni:

-   **&lt;nazwa formantu&gt;** — Nazwa formantu (na przykład przycisku), który jest renderowany w formacie HTML.
-   **(&lt;nazwa klucza&gt;)** — Nazwa klawisza na klawiaturze, dla którego tworzony jest skrót.
-   **&lt;Kod klawisza&gt;** — Kod znaku numerycznego dla klawisza, który ma być używany dla klawisza skrótu.

Oto przykład:

Anuluj (Esc) = 27; Pełny (F2) = 113

Na wszystkich stronach zawierających przycisk **Anuluj**, przycisk będzie miał ten tekst:

**(Esc) Anuluj**

Naciśnięcie klawisza Esc na klawiaturze uaktywni przycisk **Anuluj**. Aby zastosować ustawienia skrótów klawiatury i stylów do określonego urządzenia, należy utworzyć mapowanie w polu **Kryteria**. Do utworzenia mapowania trzeba użyć wyrażenia regularnego .NET, a wyrażenie musi się składać z trzech części oddzielonych pionową kreską (|), jak pokazano tutaj:

Request.UserHostAddress=&lt;adres hosta użytkownika&gt;|HostName=&lt;nazwa hosta użytkownika&gt;|Request.UserAgent=&lt;agent użytkownika&gt;

Poniżej znajdują się wyjaśnienia dotyczące części wyrażenia:

-   **&lt;adres hosta użytkownika&gt;** — Wyrażenie regularne środowiska .NET pasujące do adresu IP żądającego.
-   **&lt;nazwa hosta użytkownika&gt;** — Wyrażenie regularne środowiska .NET pasujące do nazwy sieci żądającego.
-   **&lt;agent użytkownika&gt;** — Wyrażenie regularne środowiska .NET pasujące do identyfikatora przeglądarki używanej przez żądającego.

Poniższy przykład umożliwia korzystanie z programu Internet Explorer 8:

Request.UserHostAddress=.\*|HostName=.\*|Request.UserAgent=MSIE\\s8\\.0

Można użyć menu **Wyświetl konfigurację serwera dotyczącą ustawień wyświetlania** urządzenia przenośnego, aby znaleźć informacje o konfiguracji.

## <a name="define-text-colors-for-messages"></a>Definiowanie kolorów tekstu dla wiadomości
Można użyć strony **kolory tekstu urządzenia przenośnego** do kontrolowania różnych kolorów używanych w generowanych przez system wiadomościach, takich jak komunikaty o błędach. Kolor tekstu może na przykład wskazywać cel lub priorytet komunikatu. Pokazywane są następujące typy komunikatów.

| Typ komunikatu | Opis                                                                                                                                                                            |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Domyślna      | Komunikaty domyślne używają domyślnych ustawień kolorów dla wszystkich wiadomości, jakie zdefiniowano w pliku CSS dla Portalu urządzeń przenośnych używanych w magazynie.                                                   |
| Błąd        | Komunikaty o błędach wskazują problem, który użytkownik musi rozwiązać przed kontynuowaniem.                                                                                             |
| Sukces      | Komunikat o powodzeniu potwierdza, że działanie zakończyło się pomyślnie.                                                                                                                                |
| Ostrzeżenie      | Komunikaty ostrzegawcze informują pracownika, że wystąpił problem lub, że może wystąpić problem, jeśli pracownik kontynuuje działanie. Jednakże pracownik nie musi rozwiązać problemu, aby kontynuować. |

Aby wybrać kolor, na stronie **Wybierz kolor** kliknij w palecie lub wpisz kod szesnastkowy koloru.

## <a name="define-the-date-format-to-use-on-mobile-devices"></a>Określanie formatu daty używanego na urządzeniach przenośnych
Można rozszerzyć listę zaakceptowanych formatów dat dla każdej instalacji. Na funkcja może być przydatna, jeśli chcesz podać format, który ułatwi pracownikowi wprowadzenie daty na urządzeniu przenośnym. Domyślny format zależy domyślnego języka użytkownika, który określono w polu **języka** na stronie **opcji użytkownika**. (Na tej samej stronie można skojarzyć pracownika z określonym użytkownikiem pracy magazynu). **Uwaga:** Portal urządzeń przenośnych używanych w magazynie nie używa ustawienia w polu **Format daty, godziny i liczb** na stronie **Preferencje języka i regionu**. Aby zmienić format daty, należy zapoznać się z wyrażeniami regularnymi w programie Microsoft .NET Framework. Aby uzyskać więcej informacji, zobacz temat [Wyrażenia regularne systemu .NET Framework](http://go.microsoft.com/fwlink/?LinkId=391260). Aby zdefiniować formaty daty, edytuj plik Dates.ini, który znajduje się w ścieżce Content\\Settings\\Dates.ini na serwerze Portalu urządzeń przenośnych używanych w magazynie. Ten plik zawiera wyrażenia regularne .NET do określenia formatu daty. Wyrażenie regularne musi zawierać podrzędne wyrażenia tworzące grupy nazw dla dnia, miesiąca i roku (DDMMYY), jak to przedstawiono w poniższym przykładzie:

^(?&lt;dzień&gt;\\d{2})(?&lt;miesiąc&gt;\\d{2})(?&lt;rok&gt;\\d{2})$

Każde wyrażenie podrzędnego wymaga jednej lub dwóch cyfr na dzień i miesiąc, i jednej do czterech cyfr na rok. Na przykład, poniższe wyrażenie podrzędne określa grupę nazw dla roku i wymaga minimum dwóch lub maksymalnie czterech cyfr:

(?&lt;rok&gt;\\d{2,4})

Można określić więcej niż jedno wyrażenie w tym samym pliku. Każde wyrażenie musi być w osobnym wierszu. Do analizowania daty używane jest pierwsze wyrażenie, które zostanie dostosowane.

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Konfiguracja urządzeń przenośnych do pracy w magazynie](configure-mobile-devices-warehouse.md)



