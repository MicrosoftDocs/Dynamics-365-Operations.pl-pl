---
title: "Prospekt na gotówkę"
description: "Temat zawiera omówienie rozwiązania Prospekt na gotówkę działającego między programami Dynamics 365 for Finance and Operations, Enterprise Edition a Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: a5f1ecd5f8b46287839439a963e571531ae161a7
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="prospect-to-cash"></a>Prospekt na gotówkę  

[!include[banner](../includes/banner.md)]

Rozwiązanie Prospekt na gotówkę używa [integracji danych](/common-data-service/entity-reference/dynamics-365-integration) do synchronizowania danych w całych wystąpieniach usługi Microsoft Dynamics 365 for Finance and Operations Enterprise Edition a Dynamics 365 for Sales za pośrednictwem usługi Common Data Service (CDS). Szablony Prospekt na gotówkę dostępne w funkcji integracji danych umożliwiają przepływ kont, kontaktów, produktów, ofert sprzedaży, zamówień sprzedaży i faktur sprzedaży między programami Finance a Operations and Sales. Gdy dane przepływają między programami Finance and Operations i Sales, można wykonywać działania sprzedażowe i marketingowe w programie Sales oraz i realizować zamówienia z funkcjami zarządzania zapasami w programie Finance and Operations. 

To rozwiązanie zapewnia integrację w następujących obszarach: 

-   [Obsługa kont klientów w programie Sales i synchronizowanie ich z usługą Finance and Operations](accounts-template-mapping.md)
-   [Obsługa kontaktów w programie Sales i synchronizowanie ich z usługą Finance and Operations](contacts-template-mapping.md)
-   [Obsługa produktów w programie Finance and Operations i synchronizowanie ich z programem Sales](products-template-mapping.md)
-   [Tworzenie ofert sprzedaży w programie Sales i synchronizowanie ich z usługą Finance and Operations.](sales-quotation-template-mapping.md)
-   [Tworzenie zamówień sprzedaży w programie Finance and Operations i ich synchronizacja z programem Sales](sales-order-template-mapping.md)
-   [Tworzenie faktur sprzedaży w programie Finance and Operations i ich synchronizacja z programem Sales](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-dynamics-365-for-finance-and-operations-enterprise-edition"></a>Wymagania systemowe dla rozwiązania Dynamics 365 for Finance and Operations, Enterprise Edition

Aby użyć rozwiązania Prospekt na gotówkę, należy zainstalować następujące programy:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (lipiec 2017) z aktualizacją platformy 8 (aplikacja 7.2.11792.56024 z platformą 7.0.4565.16212)

- Dwie poprawki rozwiązania Dynamics 365 for Finance and Operations, Enterprise Edition (lipiec 2017).

    -  [KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) — ta poprawka umożliwia synchronizację wiersza zamówienia sprzedaży z funkcją Integracja danych z rozwiązania Finance and Operations do programu Sales.
        
    -  [KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) — ta poprawka umożliwia synchronizację zamówienia sprzedaży z funkcją Integracja danych z rozwiązania Finance and Operations do programu Sales.
    
**Uwaga**: Należy zainstalować tylko poprawkę KB4036524, ponieważ instalacja obejmuje zmiany z poprawki KB4036461.
 
## <a name="system-requirements-for-dynamics-365-for-sales"></a>Wymagania systemowe rozwiązania Dynamics 365 for Sales

Aby użyć rozwiązania Prospekt na gotówkę, należy zainstalować następujące programy:

- Dynamics 365 for Sales wersja 1612 (8.2.1.207) (DB 8.2.1.207) online lub nowsza.
- Rozwiązanie Prospekt na gotówkę dla programu Dynamics 365 for Sales, wersja 1.14.0.0 (v14) lub nowsza.

### <a name="install-the-prospect-to-cash-solution-for-sales"></a>Instalacja rozwiązania Prospekt na gotówkę dla programu Sales

- Pobierz [Plik zip pakietu rozwiązania Prospekt na gotówkę dla programu Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) z witryny CustomerSource.

- Upewnij się, że plik zip jest odblokowany, aby podczas instalacji pakietu rozwiązania nie został wyświetlony komunikat o błędzie „Nie znaleziono pakietów importu“. Aby odblokować plik, wykonaj następujące polecenie:

    -  Kliknij plik zip prawym przyciskiem myszy.
    -  Wybierz polecenie **Właściwości**, a następnie wybierz opcję **Odblokuj**. 

- Rozpakuj i uruchom plik PackageDeployer.exe.

- Zainstaluj rozwiązanie Prospekt na gotówkę w instancji programu Sales.

    - Wybierz typ wdrożenia **Office 365**.
    - Wybierz opcję **Pokaż zaawansowane**.
    - W celu szybkiej instalacji wybierz **Region**. Jeżeli wybierzesz opcję **Nie wiem**, system wyszuka wszystkie regiony i instalacja potrwa dłużej.
    - Wprowadź informacje w polach **Nazwa użytkownika** i **Hasło** użytkownika administratora, który ma uprawnienia do instalacji.

