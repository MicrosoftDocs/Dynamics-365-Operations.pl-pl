---
title: Konfigurowanie przyszłych zdarzeń zmiany sytuacji życiowej
description: W tym artykule opisano sposób planowania przyszłych zmian sytuacji życiowej w programie Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2cb3ca03e0d9d7e5423a405f1eb0372e1c19588d
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2022
ms.locfileid: "9227994"
---
# <a name="configure-future-life-events"></a>Konfigurowanie przyszłych zdarzeń zmiany sytuacji życiowej

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [banner](../includes/preview-banner.md)]

W module Dynamics 365 Human Resources można zaplanować przyszłe zmiany sytuacji życiowej.

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Przyszłe zdarzenia zmiany sytuacji życiowej**.

2. Wybierz pozycję **Nowy**.

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | Data zdarzenia zmiany sytuacji życiowej | System przetwarza wszystkie zdarzenia w okresie rejestracji, który nastąpiły do tej daty. |
   | Zarejestrowane zdarzenie zmiany sytuacji życiowej | Data i godzina zarejestrowania zmiany sytuacji życiowej. |
   | Typ dziennika | Pokazuje, czy akcja ma jeden z następujących typów:</br></br>- **Aktualizacja** — zmiana istniejącego rekordu, który śledzi zmiany sytuacji życiowej</br></br>- **Wstawienie** — utworzenie nowego rekordu zmiany sytuacji życiowej |
   | Identyfikator typu zdarzenia zmiany sytuacji życiowej | Unikatowy identyfikator typu zmiany sytuacji życiowej. |
   | Typ zdarzenia zmiany sytuacji życiowej | Katalizator aktualizujący rejestrację pracownika na świadczenia. Aby uzyskać więcej informacji, zajrzyj do sekcji Wyzwalacze zmian sytuacji życiowej. |
   | Stan | Określa, czy zmiana sytuacji życiowej została przetworzona, czy nie. |
   | Wiersz | Numer wiersza przyszłej zmiany sytuacji życiowej. |

4. Wybierz opcję **Zapisz**. 

Możesz usunąć przyszłe wydarzenia z życia. Jeśli przetworzone przyszłe zdarzenie life zostanie usunięte, zostanie również usunięty przyszły rekord. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
