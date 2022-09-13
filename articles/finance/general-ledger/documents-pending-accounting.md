---
title: Dokumenty oczekujące na księgowanie
description: W tym artykule opisano, jak korzystać z funkcji na stronie Dokumenty oczekujące na księgowanie.
author: ryanCCarlson2
ms.date: 09/02/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: e915c248abd1c842f8f01490a49db9b824644a29
ms.sourcegitcommit: 07ed6f04dcf92a2154777333651fefe3206a817a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424375"
---
# <a name="documents-pending-accounting"></a>Dokumenty oczekujące na księgowanie

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

W tym artykule opisano, jak korzystać z funkcji na stronie **Dokumenty oczekujące na księgowanie**.

W rozwiązaniu Microsoft Dynamics 365 Finance 10.0.30 jest dostępna funkcja **Rozszerzonej wydajności dla struktury księgowania dokumentów źródłowych**. Ta funkcja usprawnia procesy księgowania dla księgowań dokumentów z włączonym dokumentem źródłowym, począwszy od procesu księgowania faktur niezależnych.

Gdy ta funkcja jest włączona, księgowanie dokumentu księgi podrzędnej jest wykonywane oddzielnie od procesu generowania księgowania lub *zapisywania w arkuszu*, który tworzy pełny szczegół księgowania przenoszony do księgi głównej. Na przykład w procesie księgowania faktury niezależnej faktura dla odbiorcy w module **Rozrachunki z odbiorcami** jest rejestrowana przed wygenerowaniem pełnego księgowania. Ta rozszerzona funkcja wydajności umożliwia szybsze rejestrowane faktur dla odbiorcy, podczas gdy generowanie księgowania jest opóźnione.

Na stronie **Dokumenty oczekujące na księgowanie** są dostępne następujące przyciski.

- **Generuj księgowanie** — prześlij dokument, który obecnie oczekuje na wygenerowanie konta w celu zapisania w arkuszu.
- **Wyświetl podziały księgowań** — wyświetla zasady podziału księgowań dla wybranego dokumentu z listy.
- **Wyświetl dziennik błędów** — wyświetla szczegóły komunikatu o błędzie istniejące dla dokumentu, w którym stan księgowania wskazuje błędy. Te same szczegóły komunikatu o błędzie można wyświetlić, wybierając łącze **Dziennik błędów** w wierszu dokumentu.

Generowanie księgowania jest wykonywane przez proces automatyzacji procesu w tle, który nosi nazwę **Procesor struktury księgowania**. Aby uzyskać więcej informacji o ustawieniach i konfiguracji wszystkich automatyzacji procesów, zobacz temat [Automatyzacja procesów](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
