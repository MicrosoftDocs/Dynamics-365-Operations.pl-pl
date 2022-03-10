---
title: Prospekt na gotówkę
description: Ten temat zawiera omówienie rozwiązania Prospekt na gotówkę działającego między Dynamics 365 Supply Chain Management i Dynamics 365 Sales.
author: Henrikan
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: b96f22d711ce5b34c2f8de5a86caf5f89dd3f337
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578999"
---
# <a name="prospect-to-cash"></a>Od prospekta do gotówki

[!include [banner](../includes/banner.md)]

Rozwiązanie Prospekt na gotówkę umożliwia bezpośrednią synchronizację między Dynamics 365 Supply Chain Management i Dynamics 365 Sales. Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży. Gdy dane przepływają, można wykonywać działania sprzedażowe i marketingowe w programie Sales oraz i realizować zamówienia z funkcjami zarządzania zapasami w programie Supply Chain Management. 

Aby uzyskać więcej informacji o integracji w procesie Prospekt na gotówkę, obejrzyj krótki film na YouTube: [Integracja scenariusza Od potencjalnego klienta do środków pieniężnych](https://www.youtube.com/watch?v=AVV9x5x-XCg).

W bieżącej wersji rozwiązania Prospekt na gotówkę udostępniono następujące typy synchronizacji bezpośredniej:

- [Synchronizowanie kont klientów bezpośrednio z rozwiązania Sales do odbiorców w Supply Chain Management](accounts-template-mapping-direct.md)
- [Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Sales](products-template-mapping-direct.md)
- [Synchronizowanie kontaktów w rozwiązaniu Sales bezpośrednio z kontaktami lub odbiorcami w rozwiązaniu Supply Chain Management](contacts-template-mapping-direct.md)
- [Synchronizowanie nagłówków ofert i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales](sales-quotation-template-mapping-sales-fin.md)
- [Synchronizowanie zamówień sprzedaży w rozwiązaniu Sales bezpośrednio z elementami w rozwiązaniu Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)
- [Synchronizowanie nagłówków faktur i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-supply-chain-management"></a>Wymagania systemowe dotyczące Supply Chain Management
Integracja w procesie Prospekt na gotówkę jest obsługiwana w następujących wersjach:

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a>Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 (grudzień 2017 r.)

- Dynamics 365 for Finance and Operations, Enterprise edition (grudzień 2017) — kompilacja aplikacji 7.3.11971.56116 z aktualizacją platformy 12 (7.0.4709.41129)

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Dynamics 365 for Finance and Operations, Enterprise edition (lipiec 2017 r.)

- Dynamics 365 for Finance and Operations, Enterprise edition (lipiec 2017 r.) — z aktualizacją platformy 8 (kompilacji aplikacji 7.2.11792.56024 z platformą w wersji 7.0.4565.16212).
- Poniżej znajduje się lista wymaganych poprawek:

  - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** — ta poprawka umożliwia synchronizację zamówienia sprzedaży między modułem Sales a modułem Supply Chain Management za pomocą funkcji integracji danych. Zapewnia również kilka innych ulepszeń.
  - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** — ta poprawka umożliwia synchronizację wiersza zamówienia sprzedaży między modułem Supply Chain Management a Sales za pomocą funkcji integracji danych.
  - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** — ta poprawka umożliwia synchronizację zamówienia sprzedaży z Supply Chain Management do Sales za pomocą funkcji integracji danych.

    > [!NOTE]
    > Należy zainstalować tylko poprawkę KB4045570, ponieważ instalacja obejmuje zmiany z innych poprawek. 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a>Dynamics 365 for Finance and Operations w wersji 1611 (listopad 2016 r.)

- Dynamics 365 for Finance and Operations w wersji 1611 (listopad 2016 r.) z aktualizacją platformy 8 lub nowszą

- Poniżej znajduje się lista wymaganych poprawek:

  - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** — umożliwia synchronizację zamówienia sprzedaży między modułem Supply Chain Management a modułem Sales za pomocą integratora danych. 
  - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** — umożliwia synchronizację nagłówka i wiersza zamówienia sprzedaży między modułem Supply Chain Management a modułem Sales za pomocą integratora danych.
  - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** — wymagana jest obsługa integracji rozwiązania Prospekt na gotówkę poprzez jednostki danych.
    
    > [!NOTE]
    > Po zainstalowaniu poprawek należy uruchomić następujące zadanie wsadowe z formularza **SalesPopulateProspectToCash**. Formularz ten jest ukryty, ponieważ jest on potrzebny tylko raz. Aby przejść do formularza, zaloguj się w środowisku i dodaj następujący fragment do adresu URL na pasku adresu przeglądarce: *&mi=action:SalesPopulateProspectToCash*, na przykład `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`. Po otwarciu formularza kliknij przycisk OK. Spowoduje to uzupełnienie nowego pola **LineCreationSequnceNumber** w tabelach **SalesLine**, **SalesQuotationLine** i **CustInvoiceTrans** unikatowymi wartościami i odświeżenie listy produktów. Jest to wymagane do działania rozwiązania Prospekt na gotówkę.


## <a name="system-requirements-for-sales"></a>Wymagania systemowe dla rozwiązania Sales

Aby skorzystać z rozwiązania Prospekt na gotówkę, należy zainstalować następujące składniki:

- Dynamics 365 Sales wersja 1612 (8.2.1.207) (DB 8.2.1.207) online lub nowsza
- Rozwiązanie Prospekt na gotówkę (P2C) dla programu Dynamics 365 Sales, wersja 1.15.0.0 lub nowsza. To rozwiązanie jest dostępne do pobrania z usługi AppSource. [Pobierz rozwiązanie Prospekt na gotówkę dla programu Dynamics 365](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]