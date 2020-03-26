---
title: Zgłaszanie wyrobów gotowych do lokalizacji niekontrolowanej przez Urządzenie karty zadań
description: Ten temat opisuje proces kończenia wyrobów gotowych w zleceniu produkcyjnym do zapasów, gdy określa lokalizację.
author: johanhoffmann
manager: AnnBe
ms.date: 01/06/2020
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
ms.openlocfilehash: 5f61c1abfb115f02e6ff314f6a3e42bb1d3b543f
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092575"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a>Zgłaszanie wyrobów gotowych do lokalizacji niekontrolowanej przez Urządzenie karty zadań 

Proces zwany Gotowym zgłoszeniem wyrobów gotowych w zleceniu produkcyjnym do magazynu. Jeśli produkt gotowy jest włączony dla zaawansowanych procesów magazynowych, produkt jest zgłaszany jako gotowy do lokalizacji zwanej lokalizacją wyjściową produkcji. Aby uzyskać informacje dotyczące konfigurowania lokalizacji produkcji, przejrzyj [Lokalizację wyjściową produkcji](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).

Jeśli lokalizacja wyjściowa produkcji jest kontrolowana przez numer rejestracyjny, należy podać numer identyfikacyjny w przypadku zgłaszania produktu jako gotowego. Pole **numeru identyfikacyjnego** jest widoczne w monicie **raportu o postępie** na stronie **Urządzenie karty zadań**. To pole jest widoczne tylko w monicie **zgłaszania postępu** podczas zgłaszania ostatniej operacji zlecenia produkcyjnego, a towar dla zlecenia produkcyjnego jest włączony do procesów zarządzania magazynem. 

Istnieją dwie opcje podawania numeru rejestracyjnego
- Użytkownik wybiera istniejący numer identyfikacyjny w polu Numer identyfikacyjny.
- Numer identyfikacyjny jest generowany automatycznie na podstawie sekwencji numerów i ustawiany domyślnie w polu numeru identyfikacyjnego.

Opcja automatycznego generowania numeru rejestracyjnego jest konfigurowana przez wybranie opcji **Generuj numer identyfikacyjny** na stronie **Konfigurowanie karty zadań dla urządzeń**.
