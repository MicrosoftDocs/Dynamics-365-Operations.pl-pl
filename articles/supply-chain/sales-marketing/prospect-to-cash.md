---
title: "Prospekt na gotówkę"
description: "Ten temat zawiera omówienie rozwiązania Prospekt na gotówkę działającego między programami Dynamics 365 for Finance and Operations, Enterprise Edition a Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 11/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 788e64476094e84eb4d438890776306c05b20582
ms.openlocfilehash: 762699cf68ec8a9df5db20d7dd33bc9248f0a36e
ms.contentlocale: pl-pl
ms.lasthandoff: 12/11/2017

---

# <a name="prospect-to-cash"></a>Prospekt na gotówkę

[!include[banner](../includes/banner.md)]

Rozwiązanie Prospekt na gotówkę umożliwia bezpośrednią synchronizację między programami Microsoft Dynamics 365 for Finance and Operations, Enterprise edition i Microsoft Dynamics 365 for Sales. Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między programami Finance and Operations a Sales. Gdy dane przepływają między programami Finance and Operations i Sales, można wykonywać działania sprzedażowe i marketingowe w programie Sales oraz i realizować zamówienia z funkcjami zarządzania zapasami w programie Finance and Operations.

W bieżącej wersji rozwiązania Prospekt na gotówkę udostępniono następujące typy synchronizacji bezpośredniej:

- [Obsługa kont klientów w programie Sales i synchronizowanie ich bezpośrednio między programem Sales a programem Finance and Operations](accounts-template-mapping-direct.md)
- [Obsługa produktów w programie Finance and Operations i synchronizowanie ich bezpośrednio z programem Sales](products-template-mapping-direct.md)
- [Obsługa kontaktów w programie Sales i synchronizowanie ich bezpośrednio z kontaktami lub odbiorcami w programie Finance and Operations](contacts-template-mapping-direct.md)
- [Synchronizowanie ofert sprzedaży bezpośrednio z rozwiązania Sales do rozwiązania Finance and Operations](sales-quotation-template-mapping-sales-fin.md)
- [Synchronizowanie zamówień sprzedaży bezpośrednio z rozwiązania Finance and Operations do rozwiązania Sales](sales-order-template-mapping-direct.md)
- [Synchronizowanie zamówień sprzedaży bezpośrednio między rozwiązaniami Sales a Finance and Operations](sales-order-template-mapping-direct-two-ways.md)
- [Synchronizowanie faktur sprzedaży bezpośrednio z rozwiązania Finance and Operations do rozwiązania Sales](sales-invoice-template-mapping-direct.md)

W starszych wersjach rozwiązania Prospekt na gotówkę funkcjonowały następujące typy synchronizacji niebezpośredniej:

- [Obsługa kont klientów w programie Sales i synchronizowanie ich z usługą Finance and Operations](accounts-template-mapping.md)
- [Obsługa kontaktów w programie Sales i synchronizowanie ich z usługą Finance and Operations](contacts-template-mapping.md)
- [Obsługa produktów w programie Finance and Operations i synchronizowanie ich z programem Sales](products-template-mapping.md)
- [Tworzenie ofert sprzedaży w programie Sales i synchronizowanie ich z usługą Finance and Operations.](sales-quotation-template-mapping.md)
- [Tworzenie zamówień sprzedaży w programie Finance and Operations i ich synchronizacja z programem Sales](sales-order-template-mapping.md)
- [Tworzenie faktur sprzedaży w programie Finance and Operations i ich synchronizacja z programem Sales](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-finance-and-operations"></a>Wymagania systemowe dla rozwiązania Finance and Operations

Aby skorzystać z rozwiązania Prospekt na gotówkę, należy zainstalować następujące składniki:

### <a name="july-2017"></a>Lipiec 2017 

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (lipiec 2017) z aktualizacją platformy 8 (aplikacja w wersji 7.2.11792.56024 z platformą w wersji 7.0.4565.16212)
- W rozwiązaniu Finance and Operations wprowadzono następujące poprawki:

    - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** — ta poprawka umożliwia synchronizację zamówienia sprzedaży między modułem Sales a modułem Finance and Operations za pomocą funkcji integracji danych. Zapewnia również kilka innych ulepszeń.
    - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** — ta poprawka umożliwia synchronizację wiersza zamówienia sprzedaży między modułem Finance and Operations a modułem Sales za pomocą funkcji integracji danych.
    - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** — ta poprawka umożliwia synchronizację zamówienia sprzedaży między modułem Finance and Operations a modułem Sales za pomocą funkcji integracji danych.

    > [!NOTE]
    > Należy zainstalować tylko poprawkę KB4045570, ponieważ instalacja ta obejmuje również zmiany z innych artykułów w bazie wiedzy Microsoft Knowledge Base (KB).

### <a name="november-2016-version-1611"></a>Listopad 2016 (wersja 1611)

- Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (listopad 2016) z aktualizacją platformy 8 lub nowszą

- W rozwiązaniu Finance and Operations wprowadzono następujące poprawki:

    - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** — umożliwia synchronizację zamówienia sprzedaży między modułem Microsoft Dynamics 365 for Finance and Operations a modułem Sales za pomocą integratora danych. 
    - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** — umożliwia synchronizację nagłówka i wiersza zamówienia sprzedaży między modułem Microsoft Dynamics 365 for Finance and Operations a modułem Sales za pomocą integratora danych.
    - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** — wymagana jest obsługa integracji rozwiązania Prospekt na gotówkę poprzez jednostki danych.
    
    > [!NOTE]
    > Po zainstalowaniu poprawek należy uruchomić poniższe zadanie wsadowe z poziomu formularza SalesPopulateProspectToCash. Formularz ten jest ukryty, ponieważ jest on potrzebny tylko raz. Aby do niego przejść, zaloguj się do środowiska, a następnie dodaj następujący łańcuch do adresu w przeglądarce: &mi=action:SalesPopulateProspectToCash, na przykład https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash, a w formularzu, który się otworzy, kliknij przycisk OK.
    Spowoduje to uzupełnienie pola „LineCreationSequnceNumber” w tabelach „SalesLine”, „SalesQuotationLine” i „CustInvoiceTrans” niepowtarzalnymi wartościami i odświeżenie listy produktów. Jest to konieczne do korzystania z integracji P2C w wersji 7.1.


## <a name="system-requirements-for-sales"></a>Wymagania systemowe dla rozwiązania Sales

Aby skorzystać z rozwiązania Prospekt na gotówkę, należy zainstalować następujące składniki:

- Microsoft Dynamics 365 for Sales wersja 1612 (8.2.1.207) (DB 8.2.1.207) online
- Rozwiązanie Prospekt na gotówkę dla programu Microsoft Dynamics 365 for Sales, wersja 1.15.0.0 (v15) 

   > [!NOTE]
   >
   > Szablony w wersji 1.0.0.0 i 1.0.0.1 są obsługiwane rozwiązaniu Prospekt na gotówkę dla oprogramowania Microsoft Dynamics 365 for Sales, wersja 1.14.1.0
   >
   > Szablony w wersji 2.0.0.0 i 2.1.0.0 są obsługiwane rozwiązaniu Prospekt na gotówkę dla oprogramowania Microsoft Dynamics 365 for Sales, wersja 1.15.0.0

### <a name="install-the-prospect-to-cash-solution-for-sales"></a>Instalacja rozwiązania Prospekt na gotówkę dla programu Sales

1. Pobierz [Plik zip pakietu rozwiązania Prospekt na gotówkę dla programu Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) z witryny CustomerSource.
2. Upewnij się, że plik .zip jest odblokowany. W przeciwnym razie przy próbie zainstalowania pakietu rozwiązania pojawi się komunikat o błędzie: „Nie znaleziono pakietów importu”. Aby odblokować plik zip, kliknij go prawym przyciskiem myszy i wybierz opcję **Właściwości**. Następnie wybierz opcję **Odblokuj**.
3. Rozpakuj i uruchom plik **PackageDeployer.exe**.
4. Zainstaluj rozwiązanie Prospekt na gotówkę w instancji programu Sales:

    1. Wybierz typ wdrożenia **Office 365**.
    2. Wybierz opcję **Pokaż zaawansowane**.
    3. W celu szybkiej instalacji wybierz region. Jeżeli wybierzesz opcję **Nie wiem**, system przeszuka wszystkie regiony i instalacja potrwa dłużej.
    4. Wprowadź nazwę użytkownika i hasło administratora z uprawnieniami do instalacji.

