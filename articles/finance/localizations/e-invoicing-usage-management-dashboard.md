---
title: Pulpit zarządzania użytkowaniem
description: W tym temacie wyjaśniono, jak korzystać z pulpitu nawigacyjnego Zarządzanie użytkowaniem w celu monitorowania korzystania z usługi fakturowania elektronicznego i zachowania zgodności z przepisami.
author: gionoder
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 411c2d33c81738dcacfb7c8feec991d0fd06fb78
ms.sourcegitcommit: 9069a8511dfe11d09a2b51d32547ba10fea48bed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/02/2021
ms.locfileid: "6130513"
---
# <a name="usage-management-dashboard"></a>Pulpit zarządzania użytkowaniem

[!include [banner](../includes/banner.md)]

Pulpit **Zarządzania użytkowaniem** pomaga monitorować wykorzystanie usługi Elektronicznego Fakturowania, a tym samym pomaga organizacji zachować zgodność z przepisami w zakresie miesięcznego wykorzystania. Zgodność jest określana poprzez obliczenie ilości zgłoszeń i porównanie jej z nabytą ilością zgłoszeń w celu zidentyfikowania wszelkich odchyleń pomiędzy ilością nabytą a wykorzystaną.

Pulpit zawiera następujące wskaźniki:

- Jeden ze wskaźników kosztów, który można wykorzystać do monitorowania zużycia dla celów zgodności licencyjnej:

    - Użycie na miesiąc (eksport)

- Trzy wskaźniki operacyjne, które można wykorzystać do śledzenia korzystania z usługi elektronicznego fakturowania w celach zarządzania:

    - Użycie według funkcji
    - Użycie według środowiska
    - Użycie na miesiąc (import)

## <a name="measurement-scope"></a>Zakres pomiaru

- Jednostka miary: 

    Na pulpicie nawigacyjnym **zarządzania używaniem** jest zliczane przesyłanie dokumentów biznesowych i importowanych faktur elektronicznych.

- Organizacja: 

    Zliczanie jest podsumowywane na podstawie identyfikatora dzierżawcy organizacji, niezależnie od liczby instancji Microsoft Dynamics 365 Finance lub Dynamics 365 Supply Chain Management, czy też liczby podmiotów prawnych, w których włączona jest usługa elektronicznego fakturowania.


## <a name="indicator-usage-per-month-export"></a>Wskaźnik: Użycie na miesiąc (eksport)

Ten wskaźnik dostarcza szczegółowych informacji na temat faktur elektronicznych wystawionych przez Twoją organizację w określonym okresie.

### <a name="scope"></a>Zakres
- Liczba dokumentów handlowych, które są przekazywane z Finance i Supply Chain Management do usługi elektronicznego fakturowania, niezależnie od liczby wierszy, które te dokumenty handlowe zawierają.
- Liczba złożonych dokumentów handlowych, które zostały pomyślnie przetworzone przez usługę Elektronicznego Fakturowania. Dokument uznaje się za przetworzony pomyślnie, gdy zakończy się przepływ czynności zdefiniowanych w konfiguracji funkcji.

> [!NOTE]
> Gdy faktura elektroniczna jest przesyłana do zewnętrznej usługi sieciowej, liczenie jest niezależne od wyników przetwarzania usługi sieciowej (akceptacja, odrzucenie lub błąd walidacji schematu). Jeśli usługa sieciowa otrzymała i odpowiedziała na żądanie z usługi fakturowania elektronicznego, zgłoszenie jest uważane za prawidłowe zliczenie.

- **Wyjątek:** Dokumenty biznesowe nie są zliczane, jeśli są ponownie przesyłane z Finance i Supply Chain Management do usługi Fakturowanie Elektroniczne, np. w sytuacji, gdy ponowne przesłanie tego samego dokumentu biznesowego jest wymagane do zmiany statusu faktury elektronicznej. Na przykład, wystawienie brazylijskiej faktury elektronicznej (dokumentu fiskalnego) jest liczone jako ważne, ale wniosek o jej anulowanie nie jest liczony.


### <a name="calculation"></a>Obliczenie

Obliczanie salda odbywa się w następujący sposób:

Saldo = Wolne + Zakupione – Używane

Gdzie:

- Wolne:
  
    Bezpłatna ilość dokumentów biznesowych, które klient może przesłać w ciągu miesiąca. Zawiera pakiet 100 dokumentów biznesowych, które można przesłać do usługi fakturowania elektronicznego. Wolny wolumen nie kumuluje się, a pozostałe saldo nie jest przenoszone na następny okres.
  
- Zakupione:
  
    Zawiera pakiet 1,000 dokumentów biznesowych, które można przesłać do usługi fakturowania elektronicznego. Ten pakiet musi być nabywany co miesiąc dla organizacji. Zakupiony wolumen nie kumuluje się, a pozostałe saldo nie jest przenoszone na następny okres.
  
- Wykorzystane: 

    Liczba zgłoszeń dokumentów biznesowych do usługi Elektronicznego Fakturowania według zdefiniowanych kryteriów.
   
> [!IMPORTANT]
> Jeśli Twoja firma planuje przekroczyć miesięczny wolumen 100 bezpłatnych zgłoszeń, wykup maksymalną ilość, aby zapewnić zgodność z zasadami licencjonowania usługi fakturowania elektronicznego firmy Microsoft.
>
> Obecnie zakupiony wolumen musi być wprowadzony ręcznie, zgodnie z datą nabycia, jako wiele pakietów po 1 000 sztuk.

## <a name="indicator-usage-by-feature"></a>Wskaźnik: użycie według funkcji

Wskaźnik pokazuje wykorzystanie funkcji elektronicznego fakturowania do wystawiania faktur elektronicznych w określonym okresie.

- Obliczenie:
  
    Użyte = zliczenie, ile razy każda z funkcji fakturowania elektronicznego została użyta podczas przesyłania dokumentów handlowych do usługi Fakturowanie Elektroniczne.

## <a name="indicator-usage-by-environment"></a>Wskaźnik: użycie według środowiska

Ten wskaźnik pokazuje wykorzystanie środowiska usług elektronicznego fakturowania w określonym okresie.

- Obliczenie:
    
    Użyte = zliczenie, ile razy każda z funkcji środowiska fakturowania elektronicznego została użyta podczas przesyłania dokumentów handlowych do usługi Fakturowanie Elektroniczne.

## <a name="indicator-usage-per-month-import"></a>Wskaźnik: Użycie na miesiąc (import)

Wskaźnik pokazuje wielkość importu faktur elektronicznych przez usługę Elektronicznego Fakturowania do Finance i Supply Chain Management w określonym okresie.

- Zakres:

    Faktury elektroniczne importowane do Finance i Supply Chain Management, niezależnie od liczby wierszy zawartych w tych fakturach elektronicznych.

- Obliczenie:

    Odebrano = liczba zaimportowanych faktur elektronicznych do Finance i Supply Chain Management.

## <a name="functions"></a>Funkcje
### <a name="purchase"></a>Zakup

Na karcie **Użycie na miesiąc (eksport)** wybierz pozycję **Zakup**, aby ręcznie zarejestrować kwotę nabytych zgłoszeń.

W tym celu należy wybrać opcję **Nowe** i wprowadzić liczbę **Pakietów** nabytych na ten dzień.

**Ilość** jest obliczana w następujący sposób:

Ilość = Pakiety * 1000

Obliczona **ilość** odzwierciedla wartość **Zakupione** ze wskaźnika **Zużycie na miesiąc (eksport)**.

### <a name="update"></a>Aktualizowanie

W okienku akcji wybierz opcję **Aktualizuj**, aby odświeżyć obliczenia i zaktualizować dane wyświetlane na stronie i na wykresie.

### <a name="reset-history-data"></a>Resetuj dane historii

W okienku akcji wybierz opcję **Resetuj dane historii**, aby odświeżyć bazę danych, z której wskaźniki są obliczane.




> [!NOTE]
> Na pulpicie nawigacyjnym **zarządzania użyciem** nie są wyświetlane kwoty pieniężne. Zamiast tego jest przedstawiana tylko liczba zliczanych zgłoszeń i zaimportowanych dokumentów.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
