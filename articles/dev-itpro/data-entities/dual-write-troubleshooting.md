---
title: Przewodnik rozwiązywania problemów z integracją danych
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji danych między Microsoft Dynamics 365 for Finance and Operations i Common Data Service.
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
ms.openlocfilehash: 5e71729dafd2ad85a01b055363d1c7056b5558b2
ms.sourcegitcommit: 3f05ede8b8acdf0550240a83a013e093b4ad043d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2019
ms.locfileid: "1873112"
---
# <a name="troubleshooting-guide-for-data-integration"></a>Przewodnik rozwiązywania problemów z integracją danych

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a>Włączanie śledzenia wtyczek w Common Data Service i sprawdzanie szczegółów błędu wtyczki podwójnego zapisu

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Jeśli wystąpi problem lub błąd podczas synchronizacji z podwójnym zapisywaniem, należy wykonać następujące kroki w celu sprawdzenia błędów w dzienniku śledzenia.

1. Aby można było sprawdzić błędy, należy włączyć dzienniki śledzenia wtyczek. Aby uzyskać instrukcje, zobacz sekcję „Wyświetlanie dzienników śledzenia” [Samouczek: Zapisz i zarejestruj wtyczkę](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).

    Teraz możesz zbadać błędy.

2. Zaloguj się w Microsoft Dynamics 365 for Sales.
3. Kliknij przycisk **Ustawienia** (symbol koła zębatego), a następnie kliknij przycisk **Ustawienia zaawansowane**.
4. W menu **Ustawienia** wybierz opcję **Dostosowywanie \> Dziennik śledzenia wtyczek**.
5. Wybierz nazwę typu **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**, aby wyświetlić szczegóły błędu.

## <a name="inspect-dual-write-synchronization-errors-in-finance-and-operations"></a>Sprawdzanie błędów synchronizacji podwójnego zapisu w programie Finance and Operations

Aby sprawdzić błędy podczas testowania, należy wykonać następujące kroki.

1. Zaloguj się do Microsoft Dynamics LifeCycle Services (LCS).
2. Otwórz projekt usługi LCS, aby przeprowadzić test podwójnego zapisywania.
3. Wybierz **Środowiska hostowane w chmurze**.
4. Utwórz połączenie pulpitu zdalnego z maszyną wirtualną (MW) Dynamics 365 for Finance and Operations za pomocą konta lokalnego pokazywanego w usługi LCS.
5. Otwórz podgląd zdarzeń. 
6. Przejdź do **Dzienniki aplikacji i usług \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacyjny**. Zostaną wyświetlone błędy i szczegóły.

## <a name="unlink-one-common-data-service-environment-from-finance-and-operations-and-link-another-environment"></a>Jak odłączyć i połączyć inne środowisko Common Data Service z programu Finance and Operations

Aby zaktualizować łącza, wykonaj następujące kroki:

1. Przejdź do środowiska Finance and Operations.
2. Otwórz Zarządzanie danymi.
3. Wybierz **Łącze do usługi CDS for Apps**.
4. Zaznacz wszystkie uruchomione mapowania, a następnie wybierz pozycję **Zatrzymaj**.
5. Zaznacz wszystkie mapowania i wybierz przycisk **Usuń**.

    > [!NOTE]
    > Opcja **Usuń** nie jest dostępna, jeśli szablon **CustomerV3-Account** jest wybrany. Wyczyść wybór tego szablonu zgodnie z wymaganiami. **CustomerV3-Account** jest starszym obsługiwanym szablonem i współpracuje z rozwiązaniem Prospekt na gotówkę. Ponieważ jest on dostępny globalnie, pojawia się pod wszystkimi szablonami.

6. Wybierz **Odłącz środowisko**.
7. Wybierz **tak**, aby potwierdzić operację.
8. Aby połączyć nowe środowisko, wykonaj kroki opisane w [przewodniku instalacji](https://aka.ms/dualwrite-docs).
