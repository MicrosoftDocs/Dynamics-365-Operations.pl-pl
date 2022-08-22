---
title: Migracja danych prospektu do gotówki z Integratora danych do podwójnego zapisu
description: W tym artykule opisano sposób migracji danych prospektu do gotówki z Integratora danych do podwójnego zapisu.
author: RamaKrishnamoorthy
ms.date: 02/01/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-26
ms.openlocfilehash: bbf5a7c2f409003816e2becf1a58ee7d7d5aafb2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289089"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Migracja danych prospektu do gotówki z Integratora danych do podwójnego zapisu

[!include [banner](../../includes/banner.md)]

Rozwiązanie Prospect to cash dostępne dla Data Integratora nie jest kompatybilne z podwójnego zapisu. Powodem tego jest indeks msdynce_AccountNumber w tabeli kont, który został dostarczony jako część rozwiązania Perspektywa do gotówki. Jeśli ten indeks istnieje, nie możesz utworzyć tego samego numeru konta klienta w dwóch różnych podmiotach prawnych. Możesz albo zacząć od nowa z podwójnego zapisu, migrując dane Perspektywa do gotówki z Data Integrator do podwójnego zapisu, albo zainstalować ostatnią wersję "dorman" rozwiązania Perspektywa do gotówki . Ten artykuł obejmuje oba te podejścia.

## <a name="install-the-last-dorman-version-of-the-data-integrator-prospect-to-cash-solution"></a>Zainstaluj ostatnią "dorman" wersję rozwiązania Data Integrator Perspektywa do gotówki

**P2C Version 15.0.0.2** jest uważana za ostatnią "uśpioną" wersję rozwiązania integrującego dane Perspektywa do gotówki. Można go pobrać z [FastTrack for Dynamics 365](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/P2C).

Należy go zainstalować ręcznie. Po instalacji wszystko pozostaje dokładnie takie samo, z wyjątkiem indeksu msdynce_AccountNumber, który został usunięty.

## <a name="steps-to-migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Kroki do migracji danych prospektu do gotówki z Integratora danych do podwójnego zapisu

Aby migrować dane prospektu do gotówki z Integratora danych do podwójnego zapisu, wykonaj poniższe kroki.

1. Uruchom zadania Integratora danych od prospektu do gotówki, aby wykonać jedną pełną synchronizację końcową. W ten sposób można mieć pewność, że oba systemy (aplikacje finansowe i operacyjne i aplikacje typu Customer Engagement) będą mieć wszystkie dane.
2. Aby zapobiec potencjalnej utracie danych, eksportuj dane prospektu do gotówki z aplikacji Microsoft Dynamics 365 Sales do pliku programu Excel lub pliku z wartościami rozdzielaymi przecinkami (CSV). Eksportuj dane z następujących jednostek:

    - [Konto](#account-table)
    - [Kontakt](#contact-table)
    - [Faktura VAT](#invoice-table)
    - Fakturowanie produktów
    - [Zamówienie](#order-table)
    - [Zamawianie produktów](#order-products-table)
    - [Produkty](#products-table)
    - [Oferta](#quote-and-quote-product-tables)
    - [Produkty z oferty](#quote-and-quote-product-tables)

3. Odinstalowywanie rozwiązania od prospektu do gotówki ze środowiska sprzedaży. Ten krok powoduje usunięcie kolumn i odpowiednich danych wprowadzonych przez rozwiązanie od prospektu do gotówki.
4. Zainstaluj rozwiązanie podwójnego zapisu.
5. Utwórz połączenie podwójnego zapisu między aplikacjami finansowymi i operacyjnymi a aplikacją Customer Engagement dla co najmniej jednej firmy.
6. Włącz mapy tabel podwójnego zapisu i uruchom wstępną synchronizację dla wymaganych danych referencyjnych. (Aby uzyskać więcej informacji, zobacz temat [Uwagi dotyczące wstępnej synchronizacji](initial-sync-guidance.md).) Przykłady wymaganych danych to grupy klientów, warunki płatności i harmonogramy płatności. Nie włączaj map podwójnego zapisu dla tabel wymagających inicjowania, takich jak tabele kont, ofert, wiersza oferty, zamówienia i wiersza zamówienia.
7. W aplikacji Customer Engagement przejdź do pozycji **Ustawienia zaawansowane \> Ustawienia systemowe \> Zarządzanie danymi \> Reguły wykrywania duplikatów** i wyłącz wszystkie reguły.
8. Zainicjuj tabele wymienione w kroku 2. Aby uzyskać instrukcje, zobacz pozostałe sekcje tego artykułu.
9. Otwórz aplikacje finansowe i operacyjne i włącz mapy tabel, takie jak konto, oferta, wiersz oferty, zamówienie i mapy tabel wiersza zamówienia. Następnie uruchom wstępną synchronizację. (Aby uzyskać więcej informacji, zobacz temat [Uwagi dotyczące wstępnej synchronizacji](initial-sync-guidance.md)). Ten proces synchronizuje dodatkowe informacje z aplikacji finansowych i operacyjnych, takie jak stan przetwarzania, adresy wysyłki i adresy rozliczeniowe, lokacje i magazyny.

## <a name="account-table"></a>Tabela Konto

1. W kolumnie **Firma** wprowadź nazwę firmy, na przykład **USMF**.
2. W kolumnie **Typ relacji** wprowadź **Klient** jako wartość statyczną. Nie można klasyfikować każdego rekordu konta jako klienta w logice biznesowej.
3. W kolumnie **Identyfikator grupy klientów** wprowadź numer grupy klientów z aplikacjach finansowych i operacyjnych. Domyślna wartość z rozwiązania od prospektu do gotówki to **10**.
4. Jeśli używasz rozwiązania od prospektu do gotówki bez dostosowania **numeru konta**, wprowadź wartość **Numer konta** w kolumnie **Numer strony**. Jeśli istnieją dostosowania i nie znasz numeru strony, pobierz te informacje z aplikacji finansowych i operacyjnych.

## <a name="contact-table"></a>Tabela Osoba kontaktowa

1. W kolumnie **Firma** wprowadź nazwę firmy, na przykład **USMF**.
2. Ustaw następujące kolumny na podstawie wartości **IsActiveCustomer** w pliku CSV:

    - Jeśli ustawienie **IsActiveCustomer** ma wartość **Yes** w pliku CSV, ustaw kolumnę **Sellable** na wartość **Yes**. W kolumnie **Identyfikator grupy klientów** wprowadź numer grupy klientów z aplikacjach finansowych i operacyjnych. Domyślna wartość z rozwiązania od prospektu do gotówki to **10**.
    - Jeśli ustawienie **IsActiveCustomer** ma wartość **No** w pliku CSV, ustaw kolumnę **Sellable** na **No** i ustaw kolumnę **Kontakt dla** na **Klient**.

3. Jeśli używasz rozwiązania od prospektu do gotówki bez dostosowania **numeru kontaktu**, ustaw następujące kolumny:

    - Migruj numer osoby kontaktowej z pliku CSV (**msdynce\_contactnumber**) do numeru osoby kontaktowej w tabeli **Osoba kontaktowa** (**msdyn\_contactnumber**).
    - Użyj wartości z tabeli **Numer osoby kontaktowej** w kolumnie **Numer strony**.
    - Użyj wartości z tabeli **Numer osoby kontaktowej** w kolumnie **Numer konta/Identyfikator osoby kontaktowej**.

## <a name="invoice-table"></a>Tabela Faktura

Ponieważ dane z tabeli **Faktura** zaprojektowano tak, aby przepływały w jedną stronę, z aplikacji finansowych i operacyjnych do aplikacji Customer Engagement, inicjowanie nie jest wymagane. Uruchom wstępną synchronizację, aby migrować wszystkie wymagane dane w aplikacjach finansowych i operacyjnych do aplikacji Customer Engagement. Aby uzyskać więcej informacji, zobacz [Uwagi dotyczące wstępnej synchronizacji](initial-sync-guidance.md).

## <a name="order-table"></a>Tabela Zamówienie

1. W kolumnie **Firma** wprowadź nazwę firmy, na przykład **USMF**.
2. Skopiuj wartość kolumny **Identyfikator zamówienia** w pliku CSV do kolumny **Numer zamówienia sprzedaży**.
3. Skopiuj wartość kolumny **Klient** w pliku CSV do kolumny **Numer klienta faktury**.
4. Skopiuj wartość kolumny **Kraj/region wysyłki** w pliku CSV do kolumny **Kraj/region wysyłki**. Przykłady tej wartości to **US** i **Stany Zjednoczone**.
5. Ustaw kolumnę **Żądana data odbioru**. Jeśli nie używasz daty przyjęcia, użyj kolumn **Żądana data dostawy**, **Data realizacji** i **Data przesłania** w pliku CSV. Przykładem tej wartości jest **2020-03-27T00:00:00Z**.
6. Ustaw kolumnę **Język**. Przykładem tej wartości jest **en-us**.
7. Ustaw kolumnę **Typ zamówienia**, używając kolumny **Oparte na pozycji**.

## <a name="order-products-table"></a>Tabela Produkty z zamówienia

- W kolumnie **Firma** wprowadź nazwę firmy, na przykład **USMF**.

## <a name="products-table"></a>Tabela Produkty

Ponieważ dane z tabeli **Produkty** zaprojektowano tak, aby przepływały w jedną stronę, z aplikacji finansowych i operacyjnych do aplikacji Customer Engagement, inicjowanie nie jest wymagane. Uruchom wstępną synchronizację, aby migrować wszystkie wymagane dane w aplikacjach finansowych i operacyjnych do aplikacji Customer Engagement. Aby uzyskać więcej informacji, zobacz [Uwagi dotyczące wstępnej synchronizacji](initial-sync-guidance.md).

## <a name="quote-and-quote-product-tables"></a>Tabele Oferta i Produkty z oferty

W przypadku tabeli **Oferta** postępuj zgodnie z instrukcjami w sekcji [Tabela Zamówienie](#order-table) wcześniej w tym artykule. W przypadku tabeli **Produkt z oferty** postępuj zgodnie z instrukcjami w sekcji [Tabela Produkty z zamówienia](#order-products-table).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

