---
title: "Scentralizowane płatności dla rozrachunków z odbiorcami"
description: "Organizacje obejmujące wiele firm mogą tworzyć i zarządzać płatnościami za pomocą jednej firmy, która obsługuje wszystkie płatności. Dlatego tych samych transakcji nie trzeba wpisywać w wielu firmach. Ten artykuł zawiera przykłady pokazujące sposób księgowania scentralizowanych płatności w różnych scenariuszach."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7208acc35e656d12b3c4f88a090f36ecfdd4fdfb
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="centralized-payments-for-accounts-receivable"></a>Scentralizowane płatności dla rozrachunków z odbiorcami

[!include[banner](../includes/banner.md)]


Organizacje obejmujące wiele firm mogą tworzyć i zarządzać płatnościami za pomocą jednej firmy, która obsługuje wszystkie płatności. Dlatego tych samych transakcji nie trzeba wpisywać w wielu firmach. Ten artykuł zawiera przykłady pokazujące sposób księgowania scentralizowanych płatności w różnych scenariuszach.

Organizacje obejmujące wiele firm mogą tworzyć i zarządzać płatnościami za pomocą firmy, która obsługuje wszystkie płatności. Dlatego tych samych transakcji nie trzeba wpisywać w wielu firmach. Ponadto organizacja oszczędza czas, bo procesy dla propozycji płatności, rozliczeń i edytowania otwartych i zamkniętych transakcji na potrzeby płatności scentralizowanych przebiegają sprawniej. 

W organizacji stosującej scentralizowane płatności występuje wiele firm dla operacji i każda firma operacyjna zarządza własnymi informacjami o należnościach za faktury. Płatności dla wszystkich operacyjnych firm są zbierane przez jedną firmę nazywaną firmą płatności. W trakcie procesu rozrachunku tworzone są odpowiednie transakcje „należne dla” i „należne od”. Użytkownik może określić, która firma w organizacji ma odbierać transakcje zrealizowanych dodatnich oraz ujemnych różnic kursowych i w jaki sposób mają być obsługiwane transakcje rabatów gotówkowych związane z płatnościami scentralizowanymi. 

Poniższe przykłady ilustrują sposób księgowania w przypadku różnych scenariuszy. Wszystkie przykłady dotyczą następującej konfiguracji:

-   Firmami są Fabrikam, Fabrikam Wschód i Fabrikam West. Płatności odbiorcy są wprowadzane do firmy Fabrikam.
-   Pole **Zaksięguj rabat gotówkowy** na stronie **Księgowanie międzyfirmowe** ma wartość **Firma wystawiająca fakturę**.
-   Pole **Zaksięguj zyski lub straty związane z wymianą walut** na stronie **Księgowanie międzyfirmowe** ma wartość **Firma dokonująca płatności**.
-   Customer Northwind Traders jest ustawiona jako odbiorca w każdej z firm. Odbiorcy z różnych firm są identyfikowani jako ten sam odbiorca, ponieważ używają tego samego identyfikatora globalnej książki adresowej.

| Identyfikator książki adresowej | Konto odbiorcy | Imię i nazwisko              | Firma  |
|-----------------|------------------|-------------------|---------------|
| 4050            | 4000             | Northwind Traders | Fabrikam      |
| 4050            | 4000             | Northwind Traders | Fabrikam Wschód |
| 4050            | 10000            | Northwind Traders | Fabrikam Zachód |

## <a name="example-1-customer-payment-of-invoice-from-another-legal-entity"></a>Przykład 1: Płatność za fakturę dla odbiorcy od innej firmy
Firma Fabrikam odbiera płatność 600,00 dla konta odbiorcy firmy Fabrikam o numerze 4000, Northwind Traders. Płatność jest rozliczana za pomocą otwartej faktury dla konta odbiorcy 4000 w firmie Fabrikam East.

### <a name="invoice-is-posted-in-fabrikam-east-for-customer-4000"></a>Faktura zostaje zaksięgowana w firmie Fabrikam East dla odbiorcy 4000

| Konto                             | Kwota debetu | Kwota kredytu |
|-------------------------------------|--------------|---------------|
| Rozrachunki z odbiorcami (Fabrikam East) | 600,00       |               |
| Sprzedaż (Fabrikam East)               |              | 600,00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>Płatność zostaje odebrana i zaksięgowana w firmie Fabrikam dla odbiorcy 4000

| Konto                        | Kwota debetu | Kwota kredytu |
|--------------------------------|--------------|---------------|
| Gotówka (Fabrikam)                | 600,00       |               |
| Rozrachunki z odbiorcami (Fabrikam) |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Płatność dla firmy Fabrikam zostaje rozliczona za pomocą faktury firmy Fabrikam East

**Księgowanie w firmie Fabrikam**

| Konto                         | Kwota debetu | Kwota kredytu |
|---------------------------------|--------------|---------------|
| Rozrachunki z odbiorcami (Fabrikam)  | 600,00       |               |
| Należne dla Fabrikam East (Fabrikam) |              | 600,00        |

**Księgowanie w firmie Fabrikam East**

| Konto                             | Kwota debetu | Kwota kredytu |
|-------------------------------------|--------------|---------------|
| Należne od Fabrikam (Fabrikam East)   | 600,00       |               |
| Rozrachunki z odbiorcami (Fabrikam East) |              | 600,00        |

## <a name="example-2-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>Przykład 2: Płatność odbiorcy za fakturę innej firmy z rabatem gotówkowym
Firma Fabrikam odbiera płatność 580,00 od odbiorcy 4000 firmy Fabrikam, Northwind Traders. Firma Fabrikam East ma otwartą fakturę dla odbiorcy 4000. Faktura ma dostępny rabat gotówkowy 20,00. Płatność jest rozliczana za pomocą otwartych faktur firmy Fabrikam East. Rabat gotówkowy jest księgowany w firmie obsługującej fakturowanie, Fabrikam East.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>Faktura zostaje zaksięgowana w firmie Fabrikam East dla odbiorcy 4000 firmy Fabrikam East

| Konto                             | Kwota debetu | Kwota kredytu |
|-------------------------------------|--------------|---------------|
| Rozrachunki z odbiorcami (Fabrikam East) | 600,00       |               |
| Sprzedaż (Fabrikam East)               |              | 600,00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>Płatność zostaje odebrana i zaksięgowana w firmie Fabrikam dla odbiorcy 4000 firmy Fabrikam

| Konto                        | Kwota debetu | Kwota kredytu |
|--------------------------------|--------------|---------------|
| Gotówka (Fabrikam)                | 600,00       |               |
| Rozrachunki z odbiorcami (Fabrikam) |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Płatność dla firmy Fabrikam zostaje rozliczona za pomocą faktury firmy Fabrikam East

**Księgowanie w firmie Fabrikam**

| Konto                         | Kwota debetu | Kwota kredytu |
|---------------------------------|--------------|---------------|
| Rozrachunki z odbiorcami (Fabrikam)  | 580,00       |               |
| Należne dla Fabrikam East (Fabrikam) |              | 580,00        |

**Księgowanie w firmie Fabrikam East**

| Konto                             | Kwota debetu | Kwota kredytu |
|-------------------------------------|--------------|---------------|
| Należne od Fabrikam (Fabrikam East)   | 580,00       |               |
| Rozrachunki z odbiorcami (Fabrikam East) |              | 580,00        |
| Rabat gotówkowy (Fabrikam East)       | 20,00        |               |
| Rozrachunki z odbiorcami (Fabrikam East) |              | 20,00         |

## <a name="example-3-customer-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-gain"></a>Przykład 3: Płatność odbiorcy za fakturę innej firmy ze zrealizowaną dodatnią różnicą kursową
Firma Fabrikam odbiera płatność 600,00 euro (EUR) od odbiorcy 4000 firmy Fabrikam, Northwind Traders. Płatność jest rozliczana za pomocą otwartej faktury dla odbiorcy 4000 w firmie Fabrikam East. W trakcie procesu rozrachunku jest generowana transakcja dodatniej różnicy kursowej.

-   Kurs wymiany EUR do USD w dniu wystawienia faktury: 1,2062
-   Kurs wymiany EUR do USD w dniu płatności: 1,2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>Faktura zostaje zaksięgowana w firmie Fabrikam East dla odbiorcy 4000 firmy Fabrikam East

| Konto                             | Kwota debetu            | Kwota kredytu           |
|-------------------------------------|-------------------------|-------------------------|
| Rozrachunki z odbiorcami (Fabrikam East) | 600,00 EUR / 723,72 USD |                         |
| Sprzedaż (Fabrikam East)               |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>Płatność zostaje odebrana i zaksięgowana w firmie Fabrikam dla odbiorcy 4000 firmy Fabrikam

| Konto                        | Kwota debetu            | Kwota kredytu           |
|--------------------------------|-------------------------|-------------------------|
| Gotówka (Fabrikam)                | 600,00 EUR / 736,62 USD |                         |
| Rozrachunki z odbiorcami (Fabrikam) |                         | 600,00 EUR / 736,62 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Płatność dla firmy Fabrikam zostaje rozliczona za pomocą faktury firmy Fabrikam East

**Księgowanie w firmie Fabrikam**

| Konto                         | Kwota debetu            | Kwota kredytu           |
|---------------------------------|-------------------------|-------------------------|
| Rozrachunki z odbiorcami (Fabrikam)  | 600,00 EUR / 736,62 USD |                         |
| Należne dla Fabrikam East (Fabrikam) |                         | 600,00 EUR / 736,62 USD |
| Należne dla Fabrikam East (Fabrikam) | 0,00 EUR / 12,90 USD    |                         |
| Zrealizowana dodatnia różnica kursowa (Fabrikam)        |                         | 0,00 EUR / 12,90 USD    |

**Księgowanie w firmie Fabrikam East**

| Konto                             | Kwota debetu            | Kwota kredytu           |
|-------------------------------------|-------------------------|-------------------------|
| Należne od Fabrikam (Fabrikam East)   | 600,00 EUR / 736,62 USD |                         |
| Rozrachunki z odbiorcami (Fabrikam East) |                         | 600,00 EUR / 736,62 USD |
| Rozrachunki z odbiorcami (Fabrikam East) | 0,00 EUR / 12,90 USD    |                         |
| Należne od Fabrikam (Fabrikam East)   |                         | 0,00 EUR / 12,90 USD    |

## <a name="example-4-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-gain"></a>Przykład 4: Płatność odbiorcy za fakturę innej firmy z rabatem gotówkowym i zrealizowaną dodatnią różnicą kursową
Firma Fabrikam księguje płatność odbiorcy 4000 firmy Fabrikam, Northwind Traders, dla otwartej faktury w firmie Fabrikam East. Faktura ma dostępny rabat gotówkowy i wygenerowaną transakcję podatku. Płatność jest rozliczana za pomocą otwartej faktury firmy Fabrikam East. W trakcie procesu rozrachunku jest generowana transakcja dodatniej różnicy kursowej. Rabat gotówkowy jest księgowany dla firmy obsługującej fakturę (Fabrikam East), a różnica kursowa jest księgowana dla firmy obsługującej płatność (Fabrikam).

-   Kurs wymiany EUR do USD w dniu wystawienia faktury: 1,2062
-   Kurs wymiany EUR do USD w dniu płatności: 1,2277

### <a name="free-text-invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-customer-4000"></a>Zostaje zaksięgowana faktura niezależna i wygenerowana transakcja podatku w firmie Fabrikam East dla odbiorcy 4000

| Konto                             | Kwota debetu            | Kwota kredytu           |
|-------------------------------------|-------------------------|-------------------------|
| Rozrachunki z odbiorcami (Fabrikam East) | 638,22 EUR / 769,82 USD |                         |
| Sprzedaż (Fabrikam East)               |                         | 600,00 EUR / 723,72 USD |
| Podatek (Fabrikam East)           |                         | 38,22 EUR / 46,10 USD   |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>Płatność zostaje odebrana i zaksięgowana w firmie Fabrikam dla odbiorcy 4000

| Konto                        | Kwota debetu            | Kwota kredytu           |
|--------------------------------|-------------------------|-------------------------|
| Gotówka (Fabrikam)                | 626,22 EUR / 768,81 USD |                         |
| Rozrachunki z odbiorcami (Fabrikam) |                         | 626,22 EUR / 768,81 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Płatność dla firmy Fabrikam zostaje rozliczona za pomocą faktury firmy Fabrikam East

**Księgowanie w firmie Fabrikam**

| Konto                         | Kwota debetu            | Kwota kredytu           |
|---------------------------------|-------------------------|-------------------------|
| Rozrachunki z odbiorcami (Fabrikam)  | 626,22 EUR / 768,81 USD |                         |
| Należne dla Fabrikam East (Fabrikam) |                         | 626,22 EUR / 768,81 USD |
| Należne dla Fabrikam East (Fabrikam) | 0,00 EUR / 13,46 USD    |                         |
| Zrealizowana dodatnia różnica kursowa (Fabrikam)        |                         | 0,00 EUR / 13,46 USD    |

**Księgowanie w firmie Fabrikam East**

| Konto                             | Kwota debetu            | Kwota kredytu           |
|-------------------------------------|-------------------------|-------------------------|
| Należne od Fabrikam (Fabrikam East)   | 626,22 EUR / 768,81 USD |                         |
| Rozrachunki z odbiorcami (Fabrikam East) |                         | 626,22 EUR / 768,81 USD |
| Rozrachunki z odbiorcami (Fabrikam East)  | 0,00 EUR / 13,46 USD    |                         |
| Należne od Fabrikam (Fabrikam East)   |                         | 0,00 EUR / 13,46 USD    |
| Rabat gotówkowy (Fabrikam East)       | 12,00 EUR / 14,47 USD   |                         |
| Rozrachunki z odbiorcami (Fabrikam East) |                         | 12,00 EUR / 14,47 USD   |

## <a name="example-5-customer-credit-note-with-primary-payment"></a>Przykład 5: Faktura korygująca odbiorcy z płatnością główną
Firma Fabrikam odbiera płatność 75,00 od odbiorcy 4000, Northwind Traders. Płatność jest rozliczana za pomocą otwartej faktury dla odbiorcy 10000 firmy Fabrikam West i otwartej faktury korygującej dla odbiorcy 4000 firmy Fabrikam East. Płatność jest wybrana jako płatność główna na stronie **Rozlicz transakcje**.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>Faktura zostaje zaksięgowana w firmie Fabrikam West dla odbiorcy 10000

| Konto                             | Kwota debetu | Kwota kredytu |
|-------------------------------------|--------------|---------------|
| Rozrachunki z odbiorcami (Fabrikam West) | 100,00       |               |
| Sprzedaż (Fabrikam West)               |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>Faktura korygująca zostaje zaksięgowana w firmie Fabrikam East dla odbiorcy 4000

| Konto                             | Kwota debetu | Kwota kredytu |
|-------------------------------------|--------------|---------------|
| Zwroty sprzedaży (Fabrikam East)       | 25,00        |               |
| Rozrachunki z odbiorcami (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>Płatność zostaje zaksięgowana w firmie Fabrikam dla odbiorcy 4000

| Konto                        | Kwota debetu | Kwota kredytu |
|--------------------------------|--------------|---------------|
| Gotówka (Fabrikam)                | 75,00        |               |
| Rozrachunki z odbiorcami (Fabrikam) |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Płatność dla firmy Fabrikam zostaje rozliczona za pomocą faktury firmy Fabrikam West i faktury korygującej firmy Fabrikam East

**Księgowanie w firmie Fabrikam**

| Konto                           | Kwota debetu | Kwota kredytu |
|-----------------------------------|--------------|---------------|
| Należne od Fabrikam East (Fabrikam) | 25,00        |               |
| Rozrachunki z odbiorcami (Fabrikam)    |              | 25,00         |
| Rozrachunki z odbiorcami (Fabrikam)    | 100,00       |               |
| Należne dla Fabrikam West (Fabrikam)   |              | 100,00        |

**Księgowanie w firmie Fabrikam East**

| Konto                             | Kwota debetu | Kwota kredytu |
|-------------------------------------|--------------|---------------|
| Rozrachunki z odbiorcami (Fabrikam East) | 25,00        |               |
| Należne dla Fabrikam (Fabrikam East)     |              | 25,00         |

**Księgowanie w firmie Fabrikam West**

| Konto                             | Kwota debetu | Kwota kredytu |
|-------------------------------------|--------------|---------------|
| Należne od Fabrikam (Fabrikam West)   | 100,00       |               |
| Rozrachunki z odbiorcami (Fabrikam West) |              | 100,00        |

## <a name="example-6-customer-credit-note-without-primary-payment"></a>Przykład 6: Faktura korygująca odbiorcy bez płatności głównej
Firma Fabrikam odbiera płatność 75,00 od odbiorcy 4000, Northwind Traders. Płatność jest rozliczana za pomocą otwartej faktury dla odbiorcy 10000 firmy Fabrikam West i otwartej faktury korygującej dla odbiorcy 4000 firmy Fabrikam East. Płatność nie jest wybrana jako płatność główna na stronie **Rozlicz transakcje**.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>Faktura zostaje zaksięgowana w firmie Fabrikam West dla odbiorcy 10000

| Konto                             | Kwota debetu | Kwota kredytu |
|-------------------------------------|--------------|---------------|
| Rozrachunki z odbiorcami (Fabrikam West) | 100,00       |               |
| Sprzedaż (Fabrikam West)               |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>Faktura korygująca zostaje zaksięgowana w firmie Fabrikam East dla odbiorcy 4000

| Konto                             | Kwota debetu | Kwota kredytu |
|-------------------------------------|--------------|---------------|
| Zwroty sprzedaży (Fabrikam East)       | 25,00        |               |
| Rozrachunki z odbiorcami (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>Płatność zostaje zaksięgowana w firmie Fabrikam dla odbiorcy 4000

| Konto                        | Kwota debetu | Kwota kredytu |
|--------------------------------|--------------|---------------|
| Gotówka (Fabrikam)                | 75,00        |               |
| Rozrachunki z odbiorcami (Fabrikam) |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Płatność dla firmy Fabrikam zostaje rozliczona za pomocą faktury firmy Fabrikam West i faktury korygującej firmy Fabrikam East

**Księgowanie w firmie Fabrikam**

| Konto                         | Kwota debetu | Kwota kredytu |
|---------------------------------|--------------|---------------|
| Rozrachunki z odbiorcami (Fabrikam)  | 75,00        |               |
| Należne dla Fabrikam West (Fabrikam) |              | 75,00         |

**Księgowanie w firmie Fabrikam East**

| Konto                              | Kwota debetu | Kwota kredytu |
|--------------------------------------|--------------|---------------|
| Rozrachunki z odbiorcami (Fabrikam East)  | 25,00        |               |
| Należne dla Fabrikam West (Fabrikam East) |              | 25,00         |

**Księgowanie w firmie Fabrikam West**

| Konto                                | Kwota debetu | Kwota kredytu |
|----------------------------------------|--------------|---------------|
| Należne od Fabrikam (Fabrikam West)      | 75,00        |               |
| Rozrachunki z odbiorcami (Fabrikam West)    |              | 75,00         |
| Należne od Fabrikam East (Fabrikam West) | 25,00        |               |
| Rozrachunki z odbiorcami (Fabrikam West)    |              | 25,00         |






