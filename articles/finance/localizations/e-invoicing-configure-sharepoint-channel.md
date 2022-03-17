---
title: Konfigurowanie kanału usługi SharePoint
description: W tym temacie wyjaśniono, jak skonfigurować kanał Microsoft SharePoint do przetwarzania przychodzących faktur elektronicznych.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ea3e14ed00b0661d3923c1839135378a8a550499
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371807"
---
# <a name="configure-a-sharepoint-channel"></a>Konfigurowanie kanału usługi SharePoint

[!include [banner](../includes/banner.md)]

Aby skonfigurować kanał Microsoft SharePoint do przetwarzania dokumentów przychodzących, wykonaj czynności opisane w [Konfiguracja połączenia z SharePoint](e-invoicing-create-sharepoint-connection.md).

Następnie możesz użyć kanału SharePoint do importowania elektronicznych faktur od dostawców z plików przechowywanych w folderach SharePoint.

1. W witrynie SharePoint można utworzyć następujące foldery:

    - **Folder główny** — folder, z których będą przetwarzane pliki przez usługę.
    - **Folder archiwum** — folder, w którym będą przechowywane przetworzone pliki
    - **Folder błędów** — folder, do którego w przypadku niepowodzenia przetwarzania system będzie przesunył pliki.

2. W Regulatory Configuration Service (RCS) wybierz utworzoną funkcję fakturowania elektronicznego. Upewnij się, że wybierzesz wersję o stanie **Wersja robocza**.
3. Na karcie **Konfiguracje** wybierz pozycję **Dodaj**.
4. W rozwijanym oknie dialogowym **Utwórz konfigurację funkcji** w grupie pól **Nowe** wybierz opcję **Konfiguracja niestandardowa**.
5. W grupie **pól Typ ustawień** wybierz opcję **Kanał danych**.
6. W polu **Wybierz kanał danych** wybierz **folder SharePoint**.
7. Wybierz opcję **Utwórz**.
8. Wybierz utworzony wiersz, a następnie wybierz opcję **Edytuj**.
9. Na karcie **Kanał danych** w sekcji **Parametry** ustaw następujące wymagane pola.

    | Pole                 | Opis |
    |-----------------------|-------------|
    | Kanał danych          | Wprowadź unikatową nazwę do identyfikowania kanału danych. Nazwa może zawierać maksymalnie 10 znaków. Podczas procesu komunikacji będzie do niego odwołanie w zasadach możliwości zastosowania oraz w połączonych aplikacjach. |
    | Adres usługi SharePoint    | Wprowadź URL SharePoint. Na przykład wpisz `<domain>.sharepoint.com`. |
    | Identyfikator aplikacji        | Wprowadź nazwę klucza tajnego Azure Key Vault, który zawiera identyfikator konta użytkownika programu SharePoint. Ten klucz tajny należy utworzyć w Key Vault i skonfigurować w środowisku usługi. Wartość jest wartością **identyfikatora aplikacji (klienta)** w formularzu [Konfiguruj połączenie SharePoint](e-invoicing-create-sharepoint-connection.md). |
    | Wpis tajny aplikacji    | Wprowadź nazwę klucza tajnego Key Vault, który zawiera hasło konta użytkownika programu SharePoint. Wartość jest wartością **Sekret rejestracji aplikacji** w formularzu [Konfiguruj połączenie SharePoint](e-invoicing-create-sharepoint-connection.md). |
    | Nazwa witryny             | Wprowadź nazwę witryny SharePoint. |
    | Nazwa biblioteki dokumentów | Wprowadź nazwę biblioteki dokumentów SharePoint. |
    | Limit czasu               | Wprowadź maksymalny czas w milisekundach (ms), przez który system powinien czekać na odpowiedź. Wartość domyślna to 10 000 ms (10 sekund). |
    | Folder główny           | Określ źródło importu plików lub folder, z którego usługa ma przetwarzać pliki. |
    | Folder archiwum        | Określ folder, w którym powinny być przechowywane przetworzone pliki. |
    | Folder błędów          | Określ folder, do którego system powinien przenieść pliki, jeśli przetwarzanie się nie powiedzie. |
    | Maksymalny rozmiar pliku         | Wprowadź maksymalny rozmiar w bajtach pojedynczego przetwarzanego pliku. Wartość domyślna to 20 000 000 bitów. |
    | Maksymalna liczba plików      | Wprowadź maksymalną liczbę plików do przetworzenia dla pojedynczej akcji. Jeśli nie chcesz ograniczać liczby plików, ustaw wartość **0** (zero). |
    | Filtr plików           | Wprowadź ciąg do filtrowania według nazwy pliku. To pole jest opcjonalne. Obsługiwana jest prosta maska, taka jak **\*smth\*.ext**, gdzie każda gwiazdka (\*) reprezentuje zero lub więcej wystąpień dowolnego znaku. Na przykład wprowadź plik **\*.pdf**, aby skonfigurować kanał do odczytu plików PDF. |
    | Niestandardowa nazwa pliku      | Wprowadź niestandardową nazwę pliku z klienta. |

10. W razie potrzeby na karcie **Reguły możliwości zastosowania** przejrzyj i zaktualizuj kryteria. Wartość w polu **Kanał** musi być równa wartości wprowadzonej w polu **Kanał danych** w poprzednim kroku.
11. Wybierz przycisk **Zapisz** i zamknij stronę.
