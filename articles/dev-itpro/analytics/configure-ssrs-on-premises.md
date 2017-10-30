---
title: "Konfigurowanie usług SQL Server Reporting Services dla wdrożenia lokalnego"
description: "Ten temat zawiera informacje dotyczące konfigurowania usługi SQL Server Reporting Services (SSRS) dla wdrożenia lokalnego."
author: sarvanisathish
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, UnifiedOperations
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: sarvanis
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5ee1b93b92516e14e9581c3b2fe6a2527403ae1e
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="configure-sql-server-reporting-services-for-an-on-premises-deployment"></a>Konfigurowanie usług SQL Server Reporting Services dla wdrożenia lokalnego

Kroki opisane w tym temacie umożliwiają skonfigurowanie usługi SQL Server Reporting Services (SSRS) dla lokalnego wdrożenia programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.

1. Otwórz aplikację Menedżer konfiguracji usługi Reporting Services.
2. Pozostaw domyślną wartość **Nazwa serwera**, która powinna być nazwa bieżącego komputera, oraz ustawienie **Wystąpienie serwera raportów** o wartości **MSSQLSERVER**. 
3. Kliknij przycisk **Połącz**.
   
   [![Połączenie konfigurowania usługi Reporting Services](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)
   
4. Kliknij kartę **Konto usługi** i sprawdź, czy ustawienia odpowiadają poniższej ilustracji.

    [![Karta Konto usługi](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)
    
5. Kliknij kartę **Adres URL usługi sieci Web** i sprawdź, czy ustawienia odpowiadają poniższej ilustracji. 

    [![Karta Adres URL usługi sieci Web](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png) 
    
6. Kliknij kartę **Baza danych** sprawdź, czy wartości w polach **Nazwa bazy danych** i **Ustawienia poświadczeń** odpowiadają poniższej ilustracji. **Uwaga:** Należy utworzyć nową bazę danych. Aby to zrobić, kliknij przycisk **Zmień bazę danych zmian**, a następnie sprawdź, czy nowa baza danych ma nazwę **DynamicsAxReportServer**.

    [![Karta Baza danych](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)
    
7. Kliknij kartę **Adres URL portalu sieci Web** i sprawdź, czy ustawienia odpowiadają poniższej ilustracji. **Uwaga:** Należy kliknąć opcję **Zastosuj**, aby utworzyć i poprawnie skonfigurować portal.

    [![Karta Adres URL portalu sieci Web](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)
    
  Po skonfigurowaniu portalu karta **Portal sieci Web** powinna wyglądać jak na poniższej ilustracji.
    [![Karta Portal sieci Web](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)
    
8. Kliknij adres URL raportów, aby wyświetlania portalu sieci Web usługi SQL Server Reporting Services. 
9.  Po przejściu do portalu utwórz nowy folder o nazwie **Dynamics**.

    [![Folder Dynamics](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)
    
10. W **Menedżerze konfiguracji usługi SQL Reporting Services** kliknij kartę **Ustawienia poczty e-mail** i sprawdź, czy ustawienia odpowiadają poniższej ilustracji.

    [![Karta Ustawienia poczty e-mail](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)
    
11. Kliknij kartę **Konto wykonywania** i sprawdź, czy ustawienia odpowiadają poniższej ilustracji.

    [![Karta Konto wykonywania](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)
    
  Nie należy zmieniać ustawień domyślnych na karcie **Klucze szyfrowania**. [![karta klucze szyfrowania](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)
    
12. Kliknij kartę **Ustawienia subskrypcji** i sprawdź, czy ustawienia odpowiadają poniższej ilustracji.

    [![Karta Ustawienia subskrypcji](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)
    
  Nie należy zmieniać ustawień domyślnych na karcie **Wdrożenie skalowalne w poziomie**. [![karta wdrożenie skalowalne w poziomie](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)
    
  Nie należy zmieniać ustawień domyślnych na karcie **Integracja usługi Power BI**. [![karta integracja usługi power bi](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png) 
    
13. Kliknij przycisk **Zakończ**, aby zamknąć **Menedżera konfiguracji usługi Reporting Services**.

    [![Zamykanie Menedżera konfiguracji usługi Reporting Services](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)
    

