---
title: Zgłaszanie wyrobów gotowych do lokalizacji niekontrolowanej przez Urządzenie karty zadań
description: Ten temat decribes proces kończenia wyrobów gotowych w zleceniu produkcyjnym do zapasów, gdy określa lokalizację.
author: johanhoffmann
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: cb809e596fd6bf3030bcee460838798435512b95
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2019
ms.locfileid: "2572136"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a>Zgłaszanie wyrobów gotowych do lokalizacji niekontrolowanej przez Urządzenie karty zadań 

Proces zwany Gotowym zgłoszeniem wyrobów gotowych w zleceniu produkcyjnym do magazynu. Jeśli produkt gotowy jest włączony dla zaawansowanych procesów magazynowych, produkt jest zgłaszany jako gotowy do lokalizacji zwanej lokalizacją wyjściową produkcji. Aby uzyskać informacje dotyczące konfigurowania lokalizacji produkcji, przejrzyj [Lokalizację wyjściową produkcji](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).

Musisz wybrać istniejący numer identyfikacyjny do wykonania tego zadania. Jeśli lokalizacja wyjściowa produkcji jest skonfigurowana do śledzenia według numeru identyfikacyjnego, podczas zgłaszania lokalizacji produkcji jako zakończonej należy uwzględnić numer identyfikacyjny. Pole **numeru identyfikacyjnego** jest widoczne w monicie **raportu o postępie** na stronie **Urządzenie karty zadań**. Pole jest widoczne tylko po wyświetleniu monitu **raportu o postępie** podczas tworzenia raportów dotyczących ostatniej operacji zlecenia produkcyjnego To pole jest wyświetlane tylko wtedy, gdy towar dla zlecenia produkcyjnego jest włączony dla procesów zarządzania magazynem. 