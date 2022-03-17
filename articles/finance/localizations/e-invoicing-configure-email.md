---
title: Konfigurowanie kanału poczty e-mail
description: W tym temacie wyjaśniono, jak skonfigurować kanał poczty e-mail w celu odbierania faktur elektronicznych.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6a5896a033212cf0f29f686eec0ab6fb3bc1d2a6
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371759"
---
# <a name="configure-an-email-channel"></a>Konfigurowanie kanału poczty e-mail

[!include [banner](../includes/banner.md)]

Jeśli utworzona funkcja fakturowania elektronicznego importuje elektroniczne faktury dostawcy z załączonych plików odbieranych pocztą e-mail, należy skonfigurować kanał konta e-mail.

1. W Regulatory Configuration Service (RCS) wybierz utworzoną funkcję fakturowania elektronicznego. Upewnij się, że wybierzesz wersję o stanie **Wersja robocza**.
2. Na karcie **Konfiguracje** wybierz pozycję **Dodaj**.
3. W rozwijanym oknie dialogowym **Utwórz konfigurację funkcji** w grupie pól **Nowe** wybierz opcję **Konfiguracja niestandardowa**.
4. W grupie **pól Typ ustawień** wybierz opcję **Kanał danych**.
5. W polu **Wybierz kanał danych** wprowadź **przychodzącą wiadomość e-mail**.
6. Wybierz opcję **Utwórz**.
7. Wybierz utworzony wiersz, a następnie wybierz opcję **Edytuj**.
8. Na karcie **Kanał danych** w sekcji **Parametry** ustaw następujące wymagane pola.

    | Pole                | Opis |
    |----------------------|-------------|
    | Kanał danych         | Wprowadź unikatową nazwę do identyfikowania kanału danych. Nazwa może zawierać maksymalnie 10 znaków. Podczas procesu komunikacji będzie do niego odwołanie w zasadach możliwości zastosowania oraz w połączonych aplikacjach. |
    | Adres serwera       | Wprowadź adres serwera dostawcy konta e-mail. Na przykład adres serwera dla dostawcy `https://outlook.live.com` to imap-mail.outlook.com. |
    | Port serwera          | Wprowadź numer portu używanego przez dostawcę konta e-mail. Na przykład port serwera dla dostawcy `https://outlook.live.com` to 993. |
    | Wpis tajny nazwy użytkownika     | Wprowadź nazwę klucza tajnego Microsoft Azure Key Vault, który zawiera identyfikator konta użytkownika poczty e-mail. Ten klucz tajny należy utworzyć w Key Vault i skonfigurować w środowisku usługi. |
    | Wpis tajny hasła użytkownika | Wprowadź nazwę klucza tajnego Key Vault, który zawiera hasło konta użytkownika poczty e-mail. |
    | Limit czasu              | Maksymalny limit czasu (w milisekundach, ms), przez który system powinien czekać na odpowiedź. Wartość domyślna to 10 000 ms (10 sekund). |
    | Folder główny          | Określ źródło importu wiadomości e-mail lub folder, z których usługa ma przetwarzać wiadomości e-mail. |
    | Folder archiwum       | Określ folder, w którym mają być przechowywane przetworzone wiadomości e-mail. Jeśli folder nie zostanie określony, system utworzy go automatycznie. |
    | Folder błędów         | Określ folder, do którego system ma przenieść wiadomości e-mail w przypadku niepowodzenia przetwarzania. Jeśli folder nie zostanie określony, system utworzy go automatycznie. |
    | Maksymalny rozmiar wiadomości     | Umożliwia wprowadzenie maksymalnego rozmiaru przetwarzanego komunikatu (w bajtach). Wartość domyślna to 20 000 000 bitów. |
    | Maksymalna liczba wiadomości   | Wprowadź maksymalną liczbę wiadomości do przetworzenia dla pojedynczej akcji. Jeśli nie chcesz ograniczać liczby wiadomości, ustaw wartość **0** (zero). |
    | Z filtru          | Wprowadź ciąg, aby filtrować według adresu nadawcy. Będą przetwarzane tylko wiadomości e-mail, w których adres nadawcy pasuje do filtru. To pole jest opcjonalne. Aby określić wiele adresów nadawcy, należy użyć średników (;) jako separatory. |
    | Filtr tematu       | Wpisz ciąg do filtrowania według tematu. Przetwarzane będą tylko e-maile, których temat pasuje do filtra. To pole jest opcjonalne. Obsługiwana jest prosta maska, taka jak **\*smth\*.ext**, gdzie każda gwiazdka (\*) reprezentuje zero lub więcej wystąpień dowolnego znaku. |
    | Filtr dat          | Umożliwia określenie daty definiującej maksymalny czas przetwarzania wiadomości (w dniach). To pole jest opcjonalne. Wartość domyślna to 30 dni. |
    | Tryb przetwarzania      | <p>Wybierz jedną z następujących opcji, aby określić, czy wszystkie załączniki w wiadomości e-mail mogą być przetwarzane razem czy też poszczególne załączniki powinny być przetwarzane osobno:</p><ul><li><b>Załącznik</b> — dla każdego załącznika w wiadomości e-mail zostanie utworzony nowy dokument elektroniczny. Jeśli na przykład jeden adres e-mail zawiera kilka plików zawierających dane faktury elektronicznej, każdy plik będzie traktowany jako nowa faktura elektroniczna w systemie.</li><li><b>Wiadomość e-mail</b> — jeden załącznik będzie traktowany jako załącznik podstawowy, a w systemie zostanie utworzona jedna faktura elektroniczna. Inne załączniki mogą być używane jako pliki pomocy technicznej.</li></ul> |

9. W sekcji **Filtr załączników** dodaj informacje o filtrowaniu plików. Przetwarzane są tylko załączniki spełniające kryteria zdefiniowanego filtru. Na przykład plik **\*.xml** będzie filtrować załączniki z rozszerzeniem nazwy pliku .xml. Nazwa załącznika jest używana w aplikacji Dynamics 365 Finance lub Dynamics 365 Supply Chain Management podczas konfiguracji.

    - Jeśli w poprzednim kroku ustawisz **w polu Tryb przetwarzania** wartość **Według wiadomości e-mail**, możesz dodać w tym miejscu wiele filtrów. Nazwa będzie identyfikować określony dokument.
    - Jeśli w polu **Tryb przetwarzania ustawiono** wartość **Według załącznika**, można dodać tylko jeden filtr.

10. W razie potrzeby na karcie **Reguły możliwości zastosowania** przejrzyj i zaktualizuj kryteria. Wartość w polu **Kanał** musi być równa wartości wprowadzonej w polu **Kanał danych** w kroku 8.
11. Wybierz przycisk **Zapisz** i zamknij stronę.
