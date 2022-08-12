---
title: Omówienie obliczania podatku
description: W tym artykule wyjaśniono ogólny zakres i funkcje obliczania podatku.
author: wangchen
ms.date: 03/02/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 817d7db5952f96fa741671166d88fffddaac84e9
ms.sourcegitcommit: 5b34b41ae74269ba639e2876bc5862ef468da1cc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/15/2022
ms.locfileid: "9166848"
---
# <a name="tax-calculation-overview"></a>Omówienie obliczania podatku

[!include [banner](../includes/banner.md)]

Obliczanie podatku to hyper-skalowalna usługa wielowątkowa, która umożliwia aparatowi Global tax engine automatyzowanie i upraszczanie procesu określania i obliczania podatków. Aparat podatków jest w pełni konfigurowalny. Elementy, które można konfigurować, obejmują model danych podlegających opodatkowaniu, kod podatku, macierz możliwości stosowania podatku oraz formułę obliczania podatku. Aparat podatków działa na podstawowej platformie usług Microsoft Azure i oferuje nowoczesne technologie oraz skalowalność.

Usługa obliczania podatku jest zintegrowana z Dynamics 365 Finance i Dynamics 365 Supply Chain Management. Można ją także zintegrować Dynamics 365 Project Operations i Dynamics 365 Commerce z innymi aplikacjami firmy i innych firm.

> [!IMPORTANT]
> Po włączeniu usługi Obliczanie podatku niektóre operacje na powiązanych danych mogą być wykonywane w centrum danych innym niż centrum danych, w którym przechowywane są dane usługi. Zapoznaj się z [Regulaminem korzystania](https://go.microsoft.com/fwlink/?linkid=2156043) przed włączeniem usługi Obliczanie podatku. Prywatność użytkowników jest dla nas bardzo ważna. Więcej informacji na ten temat znajduje się w [Oświadczeniu o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=521839).

Obliczanie podatku to aparat podatków oparty na mikrousłudze, który odznacza się wykładniczą skalowalnością i ułatwia wykonywanie następujących zadań.

- Automatyczne określanie poprawnej grupy podatków, grupy podatków dla pozycji i kodów podatku przy użyciu ulepszonego mechanizmu określania.
- Obsługa wielu numerów rejestracji podatkowej w jednej firmie i automatyczne ustalanie poprawnego numeru rejestracji podatkowej zależnie od transakcji podlegających opodatkowaniu.
- Obsługa określania podatków, obliczania, księgowania i rozliczania zamówień przeniesienia.
- Określanie konfigurowalnych formuł obliczania podatku i warunków dostosowanych do indywidualnych wymagań.
- Udostępnianie rozwiązania w zakresie określania i obliczania podatku w różnych firmach w celu ułatwienia pracy i uniknięcia błędów.
- Obsługa określania numeru rejestracji podatkowej odbiorcy i dostawcy.
- Obsługa określania kodu listy.
- Obsługa parametrów obliczania podatku na poziomie właściwości urzędu skarbowego.

Aby użyć usługi obliczania podatku, zainstaluj dodatek Obliczanie podatku z swojego projektu w usłudze Microsoft Dynamics Lifecycle Services. Następnie dokończ konfigurację w usłudze [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/) i włącz obliczanie podatku w modułach Finance i Supply Chain Management. Aby uzyskać więcej informacji, zobacz [Rozpocznij pracę z usługą podatkową](global-get-started-with-tax-calculation-service.md).

## <a name="availability"></a>Dostępność

Obliczanie podatku jest zazwyczaj dostępne w środowiskach produkcyjnych dla wszystkich odbiorców od wersji 10.0.21.

Nowe funkcje będą nadal dostarczane. Należy często sprawdzać aktualny plan wydawniczy, aby dowiadywać się o zakres obsługiwanych funkcji.

Obliczanie podatku jest wdrożone w następujących lokalizacjach geograficznych systemu Azure. Stosownie do potrzeb klientów zostanie dodanych więcej regionów geograficznych Azure.

- Azja Pacyfik
- Australia
- Kanada
- Europa
- Japonia
- Szwajcaria
- Zjednoczone Królestwo
- Stany Zjednoczone

> [!NOTE]
> Usługa obliczania podatku nie obsługuje wcześniejszych wersji Dynamics 365, jak Dynamics AX 2012 ani lokalnych wdrożeń rozwiązania Dynamics 365.

## <a name="versions"></a>Wersje
Zaleca się zaimportowanie i skonfigurowanie konfiguracji obliczania podatku z wersją, która pasuje do wersji aplikacji Finance lub Supply Chain Management.

| Wersja aplikacji Finance lub Supply Chain Management | Wersja konfiguracji podatku               |
| --------------- | --------------------------------------- |
| 10.0.18         | Konfiguracja podatku — Europa 30.12.82     |
| 10.0.19         | Konfiguracja obliczania podatku 36.38.193 |
| 10.0.20         | Konfiguracja obliczania podatku 40.43.208 |
| 10.0.21         | Konfiguracja obliczania podatku 40.48.215 |
| 10.0.22         | Konfiguracja obliczania podatku 40.48.215 |
| 10.0.23         | Konfiguracja obliczania podatku 40.50.221 |
| 10.0.24         | Konfiguracja obliczania podatku 40.50.225 |
| 10.0.25         | Konfiguracja obliczania podatku 40.50.225 |
| 10.0.26         | Konfiguracja obliczania podatku 40.54.234 |
| 10.0.27         | Konfiguracja obliczania podatku 40.54.234 |
| 10.0.28         | Konfiguracja obliczania podatku 40.54.234 |


## <a name="data-flow"></a>Przepływ danych

Poniżej znajduje się konspekt procesu przepływu danych obliczania podatku. 

1. W RCS możliwe jest wyświetlanie i importowanie konfiguracji modelu dokumentów podlegających opodatkowaniu oraz konfiguracji mapowania modelu. Jeśli jest wymagane rozszerzenie konfiguracji dla scenariusza zaawansowanego, zobacz temat [Dodawanie pól danych w konfiguracjach podatków](tax-service-add-data-fields-tax-configurations.md).
2. W RCS możliwe jest tworzenie lub modyfikowanie funkcji podatku. Funkcji podatku można używać do obsługi stawek podatkowych i reguł możliwości ich stosowania.
3. Po zakończeniu konfigurowania funkcji podatku opublikuj konfiguracje podatków i funkcje podatku z usługi RCS w repozytorium globalnym.
4. W module Finanse wybierz wersję konfiguracji funkcji podatku, która ma być dostępna dla określonej firmy.
5. W modułach Finance i Supply Chain Management transakcje należy przeprowadzać w zwykły sposób. Jeśli jest potrzebne obliczenie podatku, klient zbiera informacje z transakcji, takie jak zamówienie sprzedaży lub zamówienie zakupu, i pakuje te informacje jako ładunek. Następnie zostanie wysłane żądanie obliczenia podatku.
6. Żądanie obliczenia podatku jest odbierane z klienta i obliczanie jest wykonywane. Wynik podatku jest następnie zwracany do klienta.
7. Klient systemu Dynamics 365 otrzymuje wynik podatku i przedstawia wynik obliczenia podatku na stronie podatku.

## <a name="supported-transactions"></a>Obsługiwane transakcje

Obliczanie podatku może być włączone przez transakcje. 

W wersji 10.0.21 są obsługiwane następujące transakcje: 

- Sprzedaż

    - Oferta sprzedaży
    - Zamówienie sprzedaży
    - Potwierdzenie
    - Lista pobrania
    - Dokument dostawy
    - Faktura sprzedaży
    - Faktura kredytowa
    - Zwróć zamówienie
    - Nagłówek Opłaty dodatkowe
    - Pozostały koszt dotyczący danej pozycji

- Zakup

    - Zamówienie zakupu
    - Potwierdzenie
    - Lista przychodu
    - Dokument przyjęcia produktów
    - Faktura zakupu
    - Nagłówek Opłaty dodatkowe
    - Pozostały koszt dotyczący danej pozycji
    - Faktura kredytowa
    - Zwróć zamówienie
    - Zapotrzebowanie na zakup
    - Różne obciążenia wiersza zapotrzebowania na zakup
    - Zapytanie ofertowe
    - Różne opłaty od nagłówka zapytania ofertowego
    - Różne opłaty od wiersza zapytania ofertowego

- Zapasy

    - Przeniesienie zamówienia - wysyłka
    - Zamówienie przeniesienia - odbiór

W wersji 10.0.23 są obsługiwane następujące transakcje: 

- Faktura niezależna

W wersji 10.0.26 są obsługiwane następujące transakcje: 

- Arkusze finansowe
- Arkusz faktur od dostawców

W wersji 10.0.28 są obsługiwane następujące transakcje: 

- Arkusz płatności dostawców
- Arkusz płatności odbiorcy

## <a name="supported-countriesregions"></a>Obsługiwane kraje/regiony

Obliczanie podatku może zostać włączone zależnie od firmy. 

W wersji 10.0.21 są obsługiwane następujące kraje/regiony adresu podstawowego firmy:

- Austria
- Belgia
- Dania
- Estonia
- Finlandia
- Francja
- Niemcy
- Węgry
- Islandia
- Irlandia
- Włochy
- Łotwa
- Litwa
- Holandia
- Norwegia
- Polska
- Szwecja
- Szwajcaria
- Wielka Brytania
- Stany Zjednoczone

W wersji 10.0.22 są obsługiwane następujące kraje/regiony adresu podstawowego firmy:

- Australia
- Bahrajn
- Kanada
- Egipt
- SRA Hongkong
- Kuwejt
- Nowa Zelandia
- Oman
- Katar
- Arabia Saudyjska
- RPA
- Zjednoczone Emiraty Arabskie

W wersji 10.0.23 są obsługiwane następujące kraje/regiony adresu podstawowego firmy:

- Tajlandia
- Japonia
- Malezja
- Singapur

W wersji 10.0.24 są obsługiwane następujące kraje/regiony adresu podstawowego firmy:

- Meksyk

W wersji 10.0.26 są obsługiwane następujące kraje/regiony adresu podstawowego firmy:

- Chiny
- Republika Czeska
- Hiszpania

## <a name="related-resources"></a>Powiązane zasoby

[Rozpocznij pracę z usługą podatkową](./global-get-started-with-tax-calculation-service.md)

[Wielokrotny numer rejestracji VAT](./emea-multiple-vat-registration-numbers.md)

[Obsługa funkcji podatków dla zamówienia przeniesienia](./tasks/tax-feature-support-for-transfer-order.md)

[Jak utworzyć rozszerzenie w usłudze podatków](./tax-service-add-data-fields-tax-integration-by-extension.md)
