---
title: Project Service Automation
description: Ten temat zawiera informacje o rozwiązaniu integrującym rozwiązanie Project Service Automation z rozwiązaniem Finance and Operations. To rozwiązanie integracyjne używa funkcji integracji danych do synchronizacji danych między wystąpieniami programu Microsoft Dynamics 365 for Finance and Operations a rozwiązaniem Microsoft Dynamics 365 for Project Service Automation za pośrednictwem usługi Common Data Service (CDS).
author: KimANelson
manager: AnnBe
ms.date: 06/29/2018
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
ms.openlocfilehash: 4b1d2ae69899a2937d47f6547ee4ba72b2d1ece4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "335699"
---
# <a name="project-service-automation"></a>Project Service Automation

[!include[banner](../includes/banner.md)]

Rozwiązanie integracji rozwiązania Project Service Automation oraz Finance and Operations korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami programu Microsoft Dynamics 365 for Finance and Operations oraz Microsoft Dynamics 365 for Project Service Automation poprzez usługę Common Data Service. Szablony integracji, które są dostępne z funkcji integracji danych, umożliwiają przepływ danych na temat projektów, umów dotyczących projektów, wierszy umowy dotyczącej projektu, punktów kontrolnych wiersza umowy projektu, zadań w ramach projektu, kategorii transakcji wydatkowych, szacunków godzinowych i szacowań wydatków z rozwiązania Project Service Automation do rozwiązania Finance and Operations.

> [!NOTE]
> - Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition 7.3.0, po zainstalowaniu aktualizacji KB 4132657 i 4132660 możesz używać szablonów, aby integrować zadania projektu, kategorie transakcji wydatkowych, szacunki godzin, szacunki wydatków i wartości rzeczywiste oraz konfigurować blokowanie funkcji. Jeśli należy zresetować zasady podziału księgowań, zalecamy dodatkowo zainstalować aktualizację KB 4131710.
> - Jeśli używasz aplikacji Finance and Operations 7.3.0, należy zainstalować aktualizację 4074835. Wtedy będzie można integrować projekty o stałej cenie.
> - Jeśli używasz programu Finance and Operations w wersji 7.3.0 i przenosisz transakcje opłat z programu Project Service Automation, należy zainstalować aktualizację KB 4345320, aby te opłaty były uwzględniane w fakturze projektu.
> - Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations w wersji 8.0, masz dostęp do mechanizmów integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji.
> - Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations w wersji 8.0.1 lub nowszej, masz możliwość synchronizowania wartości rzeczywistych.

Zanim będzie można zintegrować program Project Service Automation z programem Finance and Operations, należy skonfigurować parametry integracji programu Project Service Automation. Aby uzyskać więcej informacji, zobacz [Parametry integracji aplikacji Project Service Automation](PSA-parameters.md).

To rozwiązanie integracji umożliwia bezpośrednią synchronizację w następujących scenariuszach:

- Zarządzanie umowami na projekt w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance and Operations.
- Tworzenie projektów w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance and Operations.
- Zarządzanie wierszami umowy na projekt w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance and Operations.
- Zarządzanie punktami kontrolnymi wierszy umowy na projekt w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance and Operations.
- Zarządzanie zadaniami w projekcie w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance and Operations.
- Zarządzanie kategoriami transakcji wydatkowych w programie Finance and Operations oraz synchronizowanie ich bezpośrednio z tego programu do modułu Project Service Automation.
- Tworzenie szacunków godzin w projektach w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance and Operations.
- Tworzenie szacunków wydatków w projektach w module Project Service Automation oraz synchronizowanie ich bezpośrednio z tego modułu do programu Finance and Operations.
- Tworzenie wartości rzeczywistych czasu, wydatków i opłat w projekcie w aplikacji Project Service Automation oraz tworzenie transakcji projektu w arkuszu integracji programu Project Service Automation, tak aby można je było księgować w programie Finance and Operations.

## <a name="data-synchronization"></a>Synchronizacja danych

Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane w ramach integracji pomiędzy rozwiązaniami Project Service Automation oraz Finance and Operations.

> [!NOTE]
> Nie wszystkie szablony są obecnie dostępne. Szablony będą publikowane w miarę ich finalizowania.

[![Integracja programu Project Service Automation z programem Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance-and-operations"></a>Wymagania systemowe dla rozwiązania Finance and Operations

Aby użyć aplikacji Project Service Automation dla rozwiązań integracji finansów i operacji, należy zainstalować Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 z aktualizacją platformy 12 lub nowszą.

## <a name="system-requirements-for-project-service-automation"></a>Wymagania systemowe aplikacji Project Service Automation

Aby użyć aplikacji Project Service Automation dla rozwiązań integracji dla Finance and Operations, należy zainstalować następujące składniki:

- Microsoft Dynamics 365 for Project Service Automation, wersja 9.0.0.0 lub nowsza
- Rozwiązanie Prospekt na gotówkę dla programu Microsoft Dynamics 365 for Sales, wersja 1.14.0.0 (v14) lub nowsza
- Rozwiązanie do integrowania aplikacji Project Service Automation z Finance and Operations dla programu Microsoft Dynamics 365 for Project Service Automation w wersji 1.0.0.0 lub nowszej

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a>Instalowanie rozwiązania do integrowania aplikacji Project Service Automation z Finance and Operations w wystąpieniu programu Project Service Automation

Pobierz rozwiązanie do integrowania aplikacji Project Service Automation z Finance and Operations z [Centrum pobierania Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=57016) i postępuj zgodnie z instrukcjami dołączonymi do rozwiązania.
