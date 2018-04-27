---
title: "Prospekt na gotówkę"
description: "Ten temat zawiera omówienie rozwiązania Prospekt na gotówkę działającego między programami Dynamics 365 for Finance and Operations a Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 04/03/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: bc0fa8fe3e20ae4be3e572932f99ccc54e3b746b
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="prospect-to-cash"></a>Prospekt na gotówkę

[!INCLUDE [banner](../includes/banner.md)]

Rozwiązanie Prospekt na gotówkę umożliwia bezpośrednią synchronizację między programami Dynamics 365 for Finance and Operations i Dynamics 365 for Sales. Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między programami Finance and Operations a Sales. Gdy dane przepływają między programami Finance and Operations i Sales, można wykonywać działania sprzedażowe i marketingowe w programie Sales oraz i realizować zamówienia z funkcjami zarządzania zapasami w programie Finance and Operations. 

Aby uzyskać więcej informacji o integracji w procesie Prospekt na gotówkę, obejrzyj krótki film na YouTube:

> [!Video https://www.youtube.com/embed/AVV9x5x-XCg]

W bieżącej wersji rozwiązania Prospekt na gotówkę udostępniono następujące typy synchronizacji bezpośredniej:

- [Obsługa kont klientów w programie Sales i synchronizowanie ich bezpośrednio między programem Sales a programem Finance and Operations](accounts-template-mapping-direct.md)
- [Obsługa produktów w rozwiązaniu Finance and Operations i synchronizowanie ich bezpośrednio z rozwiązaniem Sales](products-template-mapping-direct.md)
- [Obsługa kontaktów w rozwiązaniu Sales i synchronizowanie ich bezpośrednio z kontaktami lub odbiorcami w rozwiązaniu Finance and Operations](contacts-template-mapping-direct.md)
- [Synchronizowanie ofert sprzedaży bezpośrednio z rozwiązania Sales do rozwiązania Finance and Operations](sales-quotation-template-mapping-sales-fin.md)
- [Synchronizowanie zamówień sprzedaży bezpośrednio między rozwiązaniem Sales a rozwiązaniem Finance and Operations](sales-order-template-mapping-direct-two-ways.md)
- [Synchronizowanie faktur sprzedaży bezpośrednio z rozwiązania Finance and Operations do rozwiązania Sales](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-finance-and-operations"></a>Wymagania systemowe dla rozwiązania Finance and Operations
Integracja w procesie Prospekt na gotówkę jest obsługiwana w następujących wersjach:

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a>Microsoft Dynamics 365 for Finance and Operations Enterprise Edition wer. 7.3 (grudzień 2017)

- Dynamics 365 for Finance and Operations Enterprise Edition (grudzień 2017) — kompilacja aplikacji 7.3.11971.56116 z aktualizacją platformy 12 (7.0.4709.41129)

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Układ w rozwiązaniu Dynamics 365 for Finance and Operations Enterprise Edition (lipiec 2017)

- Dynamics 365 for Finance and Operations, Enterprise Edition (lipiec 2017) — z aktualizacją platformy 8 (aplikacja w wersji 7.2.11792.56024 z platformą w wersji 7.0.4565.16212).
- Poniżej znajduje się lista wymaganych poprawek:

  - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** — ta poprawka umożliwia synchronizację zamówienia sprzedaży między modułem Sales a modułem Finance and Operations za pomocą funkcji integracji danych. Zapewnia również kilka innych ulepszeń.
  - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** — ta poprawka umożliwia synchronizację wiersza zamówienia sprzedaży między modułem Finance and Operations a modułem Sales za pomocą funkcji integracji danych.
  - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** — ta poprawka umożliwia synchronizację zamówienia sprzedaży między modułem Finance and Operations a modułem Sales za pomocą funkcji integracji danych.

    > [!NOTE]
    > Należy zainstalować tylko poprawkę KB4045570, ponieważ instalacja obejmuje zmiany z innych poprawek. 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a>Wprowadzenie do rozwiązania Dynamics 365 for Finance and Operations w wersji 1611 (listopad 2016)

- Dynamics 365 for Finance and Operations w wersji 1611 (listopad 2016) z aktualizacją platformy 8 lub nowszą

- Poniżej znajduje się lista wymaganych poprawek:

  - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** — umożliwia synchronizację zamówienia sprzedaży między modułem Finance and Operations a modułem Sales za pomocą integratora danych. 
  - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** — umożliwia synchronizację nagłówka i wiersza zamówienia sprzedaży między modułem Finance and Operations a modułem Sales za pomocą integratora danych.
  - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** — wymagana jest obsługa integracji rozwiązania Prospekt na gotówkę poprzez jednostki danych.
    
    > [!NOTE]
    > Po zainstalowaniu poprawek należy uruchomić następujące zadanie wsadowe z formularza **SalesPopulateProspectToCash**. Formularz ten jest ukryty, ponieważ jest on potrzebny tylko raz. Aby przejść do formularza, zaloguj się w środowisku i dodaj następujący fragment do adresu URL na pasku adresu przeglądarce: &mi=action:SalesPopulateProspectToCash, na przykład `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`. Po otwarciu formularza kliknij przycisk OK. Spowoduje to uzupełnienie nowego pola **LineCreationSequnceNumber** w tabelach **SalesLine**, **SalesQuotationLine** i **CustInvoiceTrans** unikatowymi wartościami i odświeżenie listy produktów. Jest to wymagane do działania rozwiązania Prospekt na gotówkę.


## <a name="system-requirements-for-sales"></a>Wymagania systemowe dla rozwiązania Sales

Aby skorzystać z rozwiązania Prospekt na gotówkę, należy zainstalować następujące składniki:

- Dynamics 365 for Sales wersja 1612 (8.2.1.207) (DB 8.2.1.207) online lub nowsza
- Rozwiązanie Prospekt na gotówkę dla programu Dynamics 365 for Sales, wersja 1.15.0.0 lub nowsza. To rozwiązanie jest dostępne do pobrania z usługi AppSource. [Pobierz rozwiązanie Prospekt na gotówkę dla programu Dynamics 365](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).

