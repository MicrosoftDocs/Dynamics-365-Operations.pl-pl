---
title: "Scentralizowane płatności dla rozrachunków z dostawcami"
description: "Organizacje obejmujące wiele firm mogą tworzyć i zarządzać płatnościami za pomocą jednej firmy, która obsługuje wszystkie płatności. Dlatego tych samych płatności nie trzeba wpisywać w wielu firmach. Ten artykuł zawiera przykłady pokazujące sposób księgowania scentralizowanych płatności w różnych scenariuszach."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14341
ms.assetid: 7bd02e32-2416-4ac6-8a60-85525267fdb7
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 54329582abd36a8ca896ce731ce06ca4de58bbb0
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="centralized-payments-for-accounts-payable"></a>Scentralizowane płatności dla rozrachunków z dostawcami

[!include [banner](../includes/banner.md)]

Organizacje obejmujące wiele firm mogą tworzyć i zarządzać płatnościami za pomocą jednej firmy, która obsługuje wszystkie płatności. Dlatego tych samych płatności nie trzeba wpisywać w wielu firmach. Ten artykuł zawiera przykłady pokazujące sposób księgowania scentralizowanych płatności w różnych scenariuszach.

Organizacje obejmujące wiele firm mogą tworzyć i zarządzać płatnościami za pomocą firmy, która obsługuje wszystkie płatności. Dlatego tych samych płatności nie trzeba wpisywać w wielu firmach. Ponadto organizacja oszczędza czas, ponieważ proces płatności przebiega sprawniej.

W organizacji stosującej scentralizowane płatności występuje wiele firm dla operacji i każdej firma operacyjna zarządza własnymi fakturami od dostawców. Płatności dla wszystkich operacyjnych firm są generowane z jednej firmy nazywanej firmą płatności. W trakcie procesu rozrachunku tworzone są odpowiednie transakcje „należne dla” i „należne od”. Użytkownik może określić, która firma w organizacji ma odbierać transakcje zrealizowanych dodatnich oraz ujemnych różnic kursowych i w jaki sposób mają być obsługiwane transakcje rabatów gotówkowych związane z płatnościami międzyfirmowymi. 

Poniższe przykłady ilustrują sposób księgowania w przypadku różnych scenariuszy. Wszystkie przykłady dotyczą następującej konfiguracji:

-   Firmami są Fabrikam, Fabrikam Wschód i Fabrikam West. Płatności pochodzą z Fabrikam.
-   Pole **Zaksięguj rabat gotówkowy** na stronie **Księgowanie międzyfirmowe** ma wartość **Firma wystawiająca fakturę**.
-   Pole **Zaksięguj zyski lub straty związane z wymianą walut** na stronie **Księgowanie międzyfirmowe** ma wartość **Firma dokonująca płatności**.
-   Dostawca Fourth Coffee jest skonfigurowany jako dostawca w każdej firmie. Dostawcy z różnych firm są identyfikowani jako ten sam dostawca, ponieważ używają tego samego identyfikatora globalnej książki adresowej.

| Identyfikator katalogu | Konto dostawcy | Imię i nazwisko          | Firma  |
|--------------|----------------|---------------|---------------|
| 1050         | 3004           | Fourth Coffee | Fabrikam      |
| 1050         | 100            | Fourth Coffee | Fabrikam Wschód |
| 1050         | 3004           | Fourth Coffee | Fabrikam Zachód |

## <a name="example-1-vendor-payment-of-invoice-from-another-legal-entity"></a>Przykład 1: Płatność za fakturę dostawcy od innej firmy
Firma Fabrikam East prowadzi fakturę otwartą dla dostawcy 100, Fourth Coffee. Firma Fabrikam wprowadza i księguje płatności na koncie 3004 dostawcy firmy Fabrikam, Fourth Coffee. Płatność jest rozliczana za pomocą faktury otwartej.

### <a name="invoice-is-posted-in-fabrikam-east-for-vendor-100"></a>Faktura jest księgowana w firmie Fabrikam East dla dostawcy 100

| Konto                          | Kwota obciążenia | Kwota uznania |
|----------------------------------|--------------|---------------|
| Wydatek (Fabrikam East)          | 600,00       |               |
| Rozrachunki z dostawcami (Fabrikam East) |              | 600,00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>Płatność jest generowana i księgowana w firmie Fabrikam dla dostawcy 3004

| Konto                     | Kwota obciążenia | Kwota uznania |
|-----------------------------|--------------|---------------|
| Rozrachunki z dostawcami (Fabrikam) | 600,00       |               |
| Gotówka (Fabrikam)             |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Firma Fabrikam jest rozliczana za pomocą faktury firmy Fabrikam East

**Księgowanie firmy Fabrikam**

| Konto                           | Kwota obciążenia | Kwota uznania |
|-----------------------------------|--------------|---------------|
| Należność firmy Fabrikam East (Fabrikam) | 600,00       |               |
| Rozrachunki z dostawcami (Fabrikam)       |              | 600,00        |

**Księgowanie firmy Fabrikam East**

| Konto                          | Kwota obciążenia | Kwota uznania |
|----------------------------------|--------------|---------------|
| Rozrachunki z dostawcami (Fabrikam East) | 600,00       |               |
| Należne dla Fabrikam (Fabrikam East)  |              | 600,00        |

## <a name="example-2-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>Przykład 2: Płatność za fakturę dostawcy od innej firmy z rabatem gotówkowym
Firma Fabrikam East prowadzi fakturę otwartą dla dostawcy 100, Fourth Coffee. Na fakturze wykazano dostępny rabat gotówkowy w wysokości 20,00. Firma Fabrikam wprowadza i księguje płatność w kwocie 580,00 na koncie 3004 dostawcy firmy Fabrikam, Fourth Coffee. Płatność jest rozliczana za pomocą otwartych faktur firmy Fabrikam East. Rabat gotówkowy jest księgowany w firmie obsługującej fakturowanie, Fabrikam East.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>Faktura jest księgowana w firmie Fabrikam East dla dostawcy 100 firmy Fabrikam East

| Konto                          | Kwota obciążenia | Kwota uznania |
|----------------------------------|--------------|---------------|
| Wydatek (Fabrikam East)          | 600,00       |               |
| Rozrachunki z dostawcami (Fabrikam East) |              | 600,00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>Płatność jest generowana i księgowana w firmie Fabrikam dla dostawcy 3004 firmy Fabrikam

| Konto                     | Kwota obciążenia | Kwota uznania |
|-----------------------------|--------------|---------------|
| Rozrachunki z dostawcami (Fabrikam) | 580,00       |               |
| Gotówka (Fabrikam)             |              | 580,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Firma Fabrikam jest rozliczana za pomocą faktury firmy Fabrikam East

**Księgowanie firmy Fabrikam**

| Konto                           | Kwota obciążenia | Kwota uznania |
|-----------------------------------|--------------|---------------|
| Należność firmy Fabrikam East (Fabrikam) | 580,00       |               |
| Rozrachunki z dostawcami (Fabrikam)       |              | 580,00        |

**Księgowanie firmy Fabrikam East**

| Konto                          | Kwota obciążenia | Kwota uznania |
|----------------------------------|--------------|---------------|
| Rozrachunki z dostawcami (Fabrikam East) | 580,00       |               |
| Zobowiązanie firmy Fabrikam (Fabrikam East)  |              | 580,00        |
| Rozrachunki z dostawcami (Fabrikam East) | 20,00        |               |
| Rabat gotówkowy (Fabrikam East)    |              | 20,00         |

## <a name="example-3-vendor-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-loss"></a>Przykład 3: Płatność za fakturę dostawcy od innej firmy ze zrealizowaną ujemną różnicą kursową
Firma Fabrikam East prowadzi fakturę otwartą dla dostawcy 100, Fourth Coffee. Firma Fabrikam wprowadza i księguje płatności na koncie 3004 dostawcy firmy Fabrikam, Fourth Coffee. Płatność jest rozliczana za pomocą faktury otwartej firmy Fabrikam East. Transakcja z ujemną różnicą kursową jest generowana podczas procesu rozliczania.

-   Kurs wymiany EUR do USD w dniu wystawienia faktury: 1,2062
-   Kurs wymiany EUR do USD w dniu płatności: 1,2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>Faktura jest księgowana w firmie Fabrikam East dla dostawcy 100 firmy Fabrikam East

| Konto                          | Kwota obciążenia            | Kwota uznania           |
|----------------------------------|-------------------------|-------------------------|
| Wydatek (Fabrikam East)          | 600,00 EUR / 723,72 USD |                         |
| Rozrachunki z dostawcami (Fabrikam East) |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>Płatność jest generowana i księgowana w firmie Fabrikam dla dostawcy 3004 firmy Fabrikam

| Konto                     | Kwota obciążenia            | Kwota uznania           |
|-----------------------------|-------------------------|-------------------------|
| Rozrachunki z dostawcami (Fabrikam) | 600,00 EUR / 736,62 USD |                         |
| Gotówka (Fabrikam)             |                         | 600,00 EUR / 736,62 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Firma Fabrikam jest rozliczana za pomocą faktury firmy Fabrikam East

**Księgowanie firmy Fabrikam**

| Konto                           | Kwota obciążenia            | Kwota uznania           |
|-----------------------------------|-------------------------|-------------------------|
| Należność firmy Fabrikam East (Fabrikam) | 600,00 EUR / 736,62 USD |                         |
| Rozrachunki z dostawcami (Fabrikam)       |                         | 600,00 EUR / 736,62 USD |
| Zrealizowana ujemna różnica kursowa (Fabrikam)          | 0,00 EUR / 12,90 USD    |                         |
| Należność firmy Fabrikam East (Fabrikam) |                         | 0,00 EUR / 12,90 USD    |

**Księgowanie firmy Fabrikam East**

| Konto                          | Kwota obciążenia            | Kwota uznania           |
|----------------------------------|-------------------------|-------------------------|
| Rozrachunki z dostawcami (Fabrikam East) | 600,00 EUR / 736,62 USD |                         |
| Zobowiązanie firmy Fabrikam (Fabrikam East)  |                         | 600,00 EUR / 736,62 USD |
| Zobowiązanie firmy Fabrikam (Fabrikam East)  | 0,00 EUR / 12,90 USD    |                         |
| Rozrachunki z dostawcami (Fabrikam East) |                         | 0,00 EUR / 12,90 USD    |

## <a name="example-4-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-loss"></a>Przykład 4: Płatność za fakturę dostawcy od innej firmy z rabatem gotówkowym i ze zrealizowaną ujemną różnicą kursową
Firma Fabrikam East prowadzi fakturę otwartą dla dostawcy 100, Fourth Coffee. Faktura ma dostępny rabat gotówkowy i wygenerowaną transakcję podatku. Firma Fabrikam księguje płatności na koncie 3004 dostawcy firmy Fabrikam, Fourth Coffee. Płatność jest rozliczana za pomocą faktury otwartej firmy Fabrikam East. Transakcja z ujemną różnicą kursową jest generowana podczas procesu rozliczania. Rabat gotówkowy jest księgowany dla firmy obsługującej fakturę (Fabrikam East), a różnica kursowa jest księgowana dla firmy obsługującej płatność (Fabrikam).

-   Kurs wymiany EUR do USD w dniu wystawienia faktury: 1,2062
-   Kurs wymiany EUR do USD w dniu płatności: 1,2277

### <a name="invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-vendor-100"></a>Faktura jest księgowana, a podatek od transakcji jest generowany w firmie Fabrikam East dla dostawcy 100

| Konto                          | Kwota obciążenia            | Kwota uznania           |
|----------------------------------|-------------------------|-------------------------|
| Wydatek (Fabrikam East)          | 564,07 EUR / 680,38 USD |                         |
| Podatek (Fabrikam East)        | 35,93 EUR / 43,34 USD   |                         |
| Rozrachunki z dostawcami (Fabrikam East) |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>Płatność jest generowana i księgowana w firmie Fabrikam dla dostawcy 3004

| Konto                     | Kwota obciążenia            | Kwota uznania           |
|-----------------------------|-------------------------|-------------------------|
| Rozrachunki z dostawcami (Fabrikam) | 588,72 EUR / 722,77 USD |                         |
| Gotówka (Fabrikam East)        |                         | 588,72 EUR / 722,77 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Firma Fabrikam jest rozliczana za pomocą faktury firmy Fabrikam East

**Księgowanie firmy Fabrikam**

| Konto                           | Kwota obciążenia            | Kwota uznania           |
|-----------------------------------|-------------------------|-------------------------|
| Należność firmy Fabrikam East (Fabrikam) | 588,72 EUR / 722,77 USD |                         |
| Rozrachunki z dostawcami (Fabrikam)       |                         | 588,72 EUR / 722,77 USD |
| Zrealizowana ujemna różnica kursowa (Fabrikam)          | 0,00 EUR / 12,66 USD    |                         |
| Należność firmy Fabrikam East (Fabrikam) |                         | 0,00 EUR / 12,66 USD    |

**Księgowanie firmy Fabrikam East**

| Konto                          | Kwota obciążenia            | Kwota uznania           |
|----------------------------------|-------------------------|-------------------------|
| Rozrachunki z dostawcami (Fabrikam East) | 588,72 EUR / 722,77 USD |                         |
| Zobowiązanie firmy Fabrikam (Fabrikam East)  |                         | 588,72 EUR / 722,77 USD |
| Zobowiązanie firmy Fabrikam (Fabrikam East)   | 0,00 EUR / 12,66 USD    |                         |
| Rozrachunki z dostawcami (Fabrikam East) |                         | 0,00 EUR / 12,66 USD    |
| Rozrachunki z dostawcami (Fabrikam East) | 11,28 EUR / 13,61 USD   |                         |
| Rabat gotówkowy (Fabrikam East)    |                         | 11,28 EUR / 13,61 USD   |

## <a name="example-5-vendor-credit-note-with-primary-payment"></a>Przykład 5. Faktura korygująca dostawcy z płatnością główną
Firma Fabrikam generuje płatność w kwocie 75,00 na koncie 3004 dostawcy, Fourth Coffee. Płatność jest rozliczana za pomocą faktury otwartej dla dostawcy 3004 firmy Fabrikam West i za pomocą otwartej faktury korygującej w firmie Fabrikam East dla dostawcy 100. Płatność jest wybrana jako płatność główna na stronie **Rozlicz transakcje**.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>Faktura jest księgowana dla firmy Fabrikam West dla dostawcy 3004

| Konto                          | Kwota obciążenia | Kwota uznania |
|----------------------------------|--------------|---------------|
| Wydatek (Fabrikam West)          | 100,00       |               |
| Rozrachunki z dostawcami (Fabrikam West) |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>Faktura korygująca jest księgowana dla firmy Fabrikam East dla dostawcy 100

| Konto                          | Kwota obciążenia | Kwota uznania |
|----------------------------------|--------------|---------------|
| Rozrachunki z dostawcami (Fabrikam East) | 25,00        |               |
| Zwroty zakupów (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>Płatność jest księgowana dla firmy Fabrikam dla dostawcy 3004

| Konto                     | Kwota obciążenia | Kwota uznania |
|-----------------------------|--------------|---------------|
| Rozrachunki z dostawcami (Fabrikam) | 75,00        |               |
| Gotówka (Fabrikam)             |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Płatność firmy Fabrikam jest rozliczana za pomocą faktury firmy Fabrikam West oraz faktury korygującej firmy Fabrikam East

**Księgowanie firmy Fabrikam**

| Konto                           | Kwota obciążenia | Kwota uznania |
|-----------------------------------|--------------|---------------|
| Rozrachunki z dostawcami (Fabrikam)       | 25,00        |               |
| Zobowiązanie firmy Fabrikam East (Fabrikam)   |              | 25,00         |
| Należność firmy Fabrikam West (Fabrikam) | 100,00       |               |
| Rozrachunki z dostawcami (Fabrikam)       |              | 100,00        |

**Księgowanie firmy Fabrikam East**

| Konto                           | Kwota obciążenia | Kwota uznania |
|-----------------------------------|--------------|---------------|
| Należność firmy Fabrikam (Fabrikam East) | 25,00        |               |
| Rozrachunki z dostawcami (Fabrikam East)  |              | 25,00         |

**Księgowanie firmy Fabrikam West**

| Konto                          | Kwota obciążenia | Kwota uznania |
|----------------------------------|--------------|---------------|
| Rozrachunki z dostawcami (Fabrikam West) | 100,00       |               |
| Zobowiązanie firmy Fabrikam (Fabrikam West)  |              | 100,00        |

## <a name="example-6-vendor-credit-note-without-primary-payment"></a>Przykład 6. Faktura korygująca dostawcy bez płatności głównej
Firma Fabrikam generuje płatność w kwocie 75,00 na koncie 3004 dostawcy, Fourth Coffee. Płatność jest rozliczana za pomocą faktury otwartej dla dostawcy 3004 firmy Fabrikam West i za pomocą otwartej faktury korygującej w firmie Fabrikam East dla dostawcy 100. Płatność nie jest wybrana jako płatność główna na stronie **Rozlicz transakcje**.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>Faktura jest księgowana dla firmy Fabrikam West dla dostawcy 3004

| Konto                          | Kwota obciążenia | Kwota uznania |
|----------------------------------|--------------|---------------|
| Wydatek (Fabrikam West)          | 100,00       |               |
| Rozrachunki z dostawcami (Fabrikam West) |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>Faktura korygująca jest księgowana dla firmy Fabrikam East dla dostawcy 100

| Konto                          | Kwota obciążenia | Kwota uznania |
|----------------------------------|--------------|---------------|
| Rozrachunki z dostawcami (Fabrikam East) | 25,00        |               |
| Zwroty zakupów (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>Płatność jest księgowana dla firmy Fabrikam dla dostawcy 3004

| Konto                     | Kwota obciążenia | Kwota uznania |
|-----------------------------|--------------|---------------|
| Rozrachunki z dostawcami (Fabrikam) | 75,00        |               |
| Gotówka (Fabrikam)             |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Płatność firmy Fabrikam jest rozliczana za pomocą faktury firmy Fabrikam West oraz faktury korygującej firmy Fabrikam East

**Księgowanie firmy Fabrikam**

| Konto                           | Kwota obciążenia | Kwota uznania |
|-----------------------------------|--------------|---------------|
| Należność firmy Fabrikam West (Fabrikam) | 75,00        |               |
| Rozrachunki z dostawcami (Fabrikam)       |              | 75,00         |

**Księgowanie firmy Fabrikam East**

| Konto                                | Kwota obciążenia | Kwota uznania |
|----------------------------------------|--------------|---------------|
| Należność firmy Fabrikam West (Fabrikam East) | 25,00        |               |
| Rozrachunki z dostawcami (Fabrikam East)       |              | 25,00         |

**Księgowanie firmy Fabrikam West**

| Konto                              | Kwota obciążenia | Kwota uznania |
|--------------------------------------|--------------|---------------|
| Rozrachunki z dostawcami (Fabrikam West)     | 75,00        |               |
| Zobowiązanie firmy Fabrikam (Fabrikam West)      |              | 75,00         |
| Rozrachunki z dostawcami (Fabrikam West)     | 25,00        |               |
| Zobowiązanie firmy Fabrikam East (Fabrikam West) |              | 25,00         |






