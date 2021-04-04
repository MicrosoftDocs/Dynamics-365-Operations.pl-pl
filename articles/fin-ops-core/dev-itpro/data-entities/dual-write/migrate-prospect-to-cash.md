---
title: Migracja danych prospektu do gotówki z Integratora danych do podwójnego zapisu
description: W tym temacie opisano sposób migracji danych prospektu do gotówki z Integratora danych do podwójnego zapisu.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2021-01-04
ms.openlocfilehash: 93614e43b108671de686458887c1d6dd6fe04f7a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570571"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Migracja danych prospektu do gotówki z Integratora danych do podwójnego zapisu

[!include [banner](../../includes/banner.md)]

Aby migrować dane prospektu do gotówki z Integratora danych do podwójnego zapisu, wykonaj poniższe kroki.

1. Uruchom zadania Integratora danych od prospektu do gotówki, aby wykonać jedną pełną synchronizację końcową. W ten sposób można mieć pewność, że oba systemy (aplikacje Finance and Operations i aplikacje typu Customer Engagement) będą mieć wszystkie dane.
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
5. Utwórz połączenie podwójnego zapisu między aplikacją Finance and Operations a aplikacją Customer Engagement dla co najmniej jednej firmy.
6. Włącz mapy tabel podwójnego zapisu i uruchom wstępną synchronizację dla wymaganych danych referencyjnych. (Aby uzyskać więcej informacji, zobacz temat [Uwagi dotyczące wstępnej synchronizacji](initial-sync-guidance.md).) Przykłady wymaganych danych to grupy klientów, warunki płatności i harmonogramy płatności. Nie włączaj map podwójnego zapisu dla tabel wymagających inicjowania, takich jak tabele kont, ofert, wiersza oferty, zamówienia i wiersza zamówienia.
7. W aplikacji Customer Engagement przejdź do pozycji **Ustawienia zaawansowane \> Ustawienia systemowe \> Zarządzanie danymi \> Reguły wykrywania duplikatów** i wyłącz wszystkie reguły.
8. Zainicjuj tabele wymienione w kroku 2. Aby uzyskać instrukcje, zobacz pozostałe sekcje tego tematu.
9. Otwórz aplikację Finance and Operations i włącz mapy tabel, takie jak konto, oferta, wiersz oferty, zamówienie i mapy tabel wiersza zamówienia. Następnie uruchom wstępną synchronizację. (Aby uzyskać więcej informacji, zobacz temat [Uwagi dotyczące wstępnej synchronizacji](initial-sync-guidance.md)). Ten proces synchronizuje dodatkowe informacje z aplikacji Finance and Operations, takie jak stan przetwarzania, adresy wysyłki i adresy rozliczeniowe, lokacje i magazyny.

## <a name="account-table"></a>Tabela Konto

1. W kolumnie **Firma** wprowadź nazwę firmy, na przykład **USMF**.
2. W kolumnie **Typ relacji** wprowadź **Klient** jako wartość statyczną. Nie można klasyfikować każdego rekordu konta jako klienta w logice biznesowej.
3. W kolumnie **Identyfikator grupy klientów** wprowadź numer grupy klientów z aplikacji Finance and Operations. Domyślna wartość z rozwiązania od prospektu do gotówki to **10**.
4. Jeśli używasz rozwiązania od prospektu do gotówki bez dostosowania **numeru konta**, wprowadź wartość **Numer konta** w kolumnie **Numer strony**. Jeśli istnieją dostosowania i nie znasz numeru strony, pobierz te informacje z aplikacji Finance and Operations.

## <a name="contact-table"></a>Tabela Osoba kontaktowa

1. W kolumnie **Firma** wprowadź nazwę firmy, na przykład **USMF**.
2. Ustaw następujące kolumny na podstawie wartości **IsActiveCustomer** w pliku CSV:

    - Jeśli ustawienie **IsActiveCustomer** ma wartość **Yes** w pliku CSV, ustaw kolumnę **Sellable** na wartość **Yes**. W kolumnie **Identyfikator grupy klientów** wprowadź numer grupy klientów z aplikacji Finance and Operations. Domyślna wartość z rozwiązania od prospektu do gotówki to **10**.
    - Jeśli ustawienie **IsActiveCustomer** ma wartość **No** w pliku CSV, ustaw kolumnę **Sellable** na **No** i ustaw kolumnę **Kontakt dla** na **Klient**.

3. Jeśli używasz rozwiązania od prospektu do gotówki bez dostosowania **numeru kontaktu**, ustaw następujące kolumny:

    - Migruj numer osoby kontaktowej z pliku CSV (**msdynce\_contactnumber**) do numeru osoby kontaktowej w tabeli **Osoba kontaktowa** (**msdyn\_contactnumber**).
    - Użyj wartości z tabeli **Numer osoby kontaktowej** w kolumnie **Numer strony**.
    - Użyj wartości z tabeli **Numer osoby kontaktowej** w kolumnie **Numer konta/Identyfikator osoby kontaktowej**.

## <a name="invoice-table"></a>Tabela Faktura

Ponieważ dane z tabeli **Faktura** zaprojektowano tak, aby przepływały w jedną stronę, z aplikacji Finance and Operations do aplikacji Customer Engagement, inicjowanie nie jest wymagane. Uruchom wstępną synchronizację, aby migrować wszystkie wymagane dane z aplikacji Finance and Operations do aplikacji Customer Engagement. Aby uzyskać więcej informacji, zobacz [Uwagi dotyczące wstępnej synchronizacji](initial-sync-guidance.md).

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

Ponieważ dane z tabeli **Produkty** zaprojektowano tak, aby przepływały w jedną stronę, z aplikacji Finance and Operations do aplikacji Customer Engagement, inicjowanie nie jest wymagane. Uruchom wstępną synchronizację, aby migrować wszystkie wymagane dane z aplikacji Finance and Operations do aplikacji Customer Engagement. Aby uzyskać więcej informacji, zobacz [Uwagi dotyczące wstępnej synchronizacji](initial-sync-guidance.md).

## <a name="quote-and-quote-product-tables"></a>Tabele Oferta i Produkty z oferty

W przypadku tabeli **Oferta** postępuj zgodnie z instrukcjami w sekcji [Tabela Zamówienie](#order-table) wcześniej w tym temacie. W przypadku tabeli **Produkt z oferty** postępuj zgodnie z instrukcjami w sekcji [Tabela Produkty z zamówienia](#order-products-table).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]