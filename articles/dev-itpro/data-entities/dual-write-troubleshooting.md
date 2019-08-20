---
title: Przewodnik rozwiązywania problemów z integracją danych
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji między Microsoft Dynamics 365 for Finance and Operations i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: ca62a6b3aa64ec2383ee3ded3b7bbf4650a41166
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797282"
---
# <a name="troubleshooting-guide-for-data-integration"></a>Przewodnik rozwiązywania problemów z integracją danych

## <a name="enable-plugin-trace-in-common-data-service-and-check-the-dual-write-plugin-error-details"></a>Włączanie śledzenia wtyczki w Common Data Service i sprawdzanie szczegółów błędu wtyczki podwójnego zapisu

Jeśli występu problem lub błąd z synchronizacją podwójnego zapisu, można sprawdzić błędy w dzienniku śledzenia:

1. Zanim możliwe będzie sprawdzenie błędów, należy włączyć śledzenie wtyczek, korzystając z instrukcji w temacie pomocy [Rejestrowanie wtyczki](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs), aby włączyć śledzenie wtyczek. Teraz możesz sprawdzić błędy.
2. Zaloguj się do usługi Dynamics 365 for Sales.
3. Kliknij ikonę Ustawienia (koło zębate) i wybierz opcję **Ustawienia zaawansowane**.
4. W menu **Ustawienia** wybierz opcję **Dostosowywanie > Dziennik śledzenia wtyczek**.
5. Kliknij nazwę typu **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**, aby wyświetlić szczegóły błędu.

## <a name="check-dual-write-synchronization-errors-in-finance-and-operations"></a>Sprawdzanie błędów synchronizacji podwójnego zapisu w programie Finance and Operations

Można sprawdzić błędy podczas testowania, wykonując następujące kroki:

+ Zaloguj się do LifeCycle Services (LCS).
+ Otwórz projekt LCS, który wybrano do sprawdzenia podwójnego zapisu.
+ Otwórz Środowiska hostowane w chmurze.
+ Użyj pulpitu zdalnego, aby skorzystać z Finance and Operations VM przy użyciu lokalnego konta wyświetlanego w LCS.
+ Otwórz przeglądarkę zdarzeń. 
+ Przejdź do **Dzienniki aplikacji i usług > Microsoft > Dynamics > AX-DualWriteSync > Operacyjny**. Zostaną wyświetlone błędy i szczegóły.

## <a name="how-to-unlink-and-link-another-common-data-service-environment-from-finance-and-operations"></a>Jak odłączyć i połączyć inne środowisko Common Data Service z programu Finance and Operations

Można aktualizować łącza, wykonując następujące kroki:

+ Przejdź do środowiska Finance and Operations.
+ Otwórz Zarządzanie danymi.
+ Kliknij **Łącze do usługi CDS for Apps**.
+ Zaznacz wszystkie uruchomione mapowania i kliknij przycisk **Zatrzymaj**. 
+ Zaznacz wszystkie mapowania i kliknij przycisk **Usuń**.

    > [!NOTE]
    > Opcja **Usuń** nie pojawi się, jeśli szablon **CustomerV3-Account** jest wybrany. W razie potrzeby usuń zaznaczenie. **CustomerV3-Account** jest starszym obsługiwanym szablonem i współpracuje z rozwiązaniem Prospekt na gotówkę. Ponieważ jest on dostępny globalnie, pojawia się pod wszystkimi szablonami.

+ Kliknij **Odłącz środowisko**.
+ Kliknij **Tak**, aby potwierdzić.
+ Aby połączyć nowe środowisko, wykonaj kroki opisane w [przewodniku instalacji](https://aka.ms/dualwrite-docs).

