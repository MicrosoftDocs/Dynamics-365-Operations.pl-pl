---
title: Omówienie rozwiązania Project Service Automation
description: Ten temat zawiera informacje dotyczące funkcji integracji rozwiązania Dynamics 365 Project Service Automation do Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31d72591041f8d8cc327aa7c6578c15731ba13c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250560"
---
# <a name="project-service-automation-overview"></a>Omówienie rozwiązania Project Service Automation

[!include[banner](../includes/banner.md)]

Rozwiązanie integracji rozwiązania Project Service Automation oraz Finance korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami programu Dynamics 365 Finance oraz Dynamics 365 Project Service Automation poprzez usługę Common Data Service. Szablony integracji, które są dostępne z funkcji integracji danych, umożliwiają przepływ danych na temat projektów, umów dotyczących projektów, wierszy umowy dotyczącej projektu, punktów kontrolnych wiersza umowy projektu, zadań w ramach projektu, kategorii transakcji wydatkowych, szacunków godzinowych i szacowań wydatków z rozwiązania Project Service Automation do rozwiązania Finance.

> [!NOTE]
> - Jeśli używasz wersji 7.3.0, należy zainstalować poprawkę KB 4074835. Wtedy będzie można integrować projekty o stałej cenie.
> - Jeśli używasz wersji 7.3.0 i przenosisz transakcje opłat z programu Project Service Automation, należy zainstalować aktualizację KB 4345320, aby te opłaty były uwzględniane w fakturze projektu.
> - Jeśli używasz wersji 8.0, masz dostęp do mechanizmów integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji.
> - Jeśli używasz wersji 8.0.1 lub nowszej, masz możliwość synchronizowania wartości rzeczywistych.

Zanim będzie można zintegrować program Project Service Automation z programem Finance, należy skonfigurować parametry integracji programu Project Service Automation. Aby uzyskać więcej informacji, zobacz [Parametry integracji aplikacji Project Service Automation](PSA-parameters.md).

To rozwiązanie integracji umożliwia bezpośrednią synchronizację w następujących scenariuszach:

- Zarządzanie umowami na projekt w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance
- Tworzenie projektów w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance.
- Zarządzanie wierszami umów na projekt w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance.
- Zarządzanie kroków miliowych wierszy umów na projekt w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance.
- Zarządzanie zadaniami na projekt w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance.
- Zarządzanie kategoriami transakcji wydatkowych w programie Finance oraz synchronizowanie ich bezpośrednio z tego programu do modułu Project Service Automation.
- Tworzenie szacunków godzin w projektach w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance.
- Tworzenie wydatków w projektach w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance.
- Tworzenie wartości rzeczywistych czasu, wydatków i opłat w projekcie w aplikacji Project Service Automation oraz tworzenie transakcji projektu w arkuszu integracji programu Project Service Automation, tak aby można je było księgować w programie Finance.

## <a name="data-synchronization"></a>Synchronizacja danych

Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane w ramach integracji pomiędzy rozwiązaniami Project Service Automation oraz Finance.

> [!NOTE]
> Nie wszystkie szablony są obecnie dostępne. Szablony będą publikowane w miarę ich finalizowania.

[![Parametry integracji Project Service Automation z Finance](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance"></a>Wymagania systemowe dla rozwiązania Finance

Aby użyć aplikacji Project Service Automation dla rozwiązań integracji Finance, należy zainstalować Enterprise edition 7.3 z aktualizacją platformy 12 lub nowszą.

## <a name="system-requirements-for-project-service-automation"></a>Wymagania systemowe aplikacji Project Service Automation

Aby użyć aplikacji Project Service Automation dla rozwiązań integracji dla Finance, należy zainstalować następujące składniki:

- Dynamics 365 Project Service Automation, wersja 9.0.0.0 lub nowsza
- Rozwiązanie Prospekt na gotówkę dla programu Dynamics 365 Sales, wersja 1.14.0.0 (v14) lub nowsza.
- Rozwiązanie do integrowania aplikacji Project Service Automation z Finance dla programu Dynamics 365 Project Service Automation w wersji 1.0.0.0 lub nowszej

## <a name="install-the-project-service-automation-to-finance-integration-solution-in-your-project-service-automation-instance"></a>Instalowanie rozwiązania do integrowania aplikacji Project Service Automation z Finance w wystąpieniu programu Project Service Automation

Pobierz rozwiązanie do integrowania aplikacji Project Service Automation z Finance z [Centrum pobierania Microsoft](https://www.microsoft.com/download/details.aspx?id=57016) i postępuj zgodnie z instrukcjami dołączonymi do rozwiązania.
