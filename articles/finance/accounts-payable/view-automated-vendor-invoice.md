---
title: Wyświetlanie wyników automatyzacji faktur od dostawców (wersja zapoznawcza)
description: W tym temacie opisano sposób wyświetlania stanu faktur od dostawców w zautomatyzowanym procesie przesyłania do przepływu pracy.
author: abruer
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ec49a621e24b6373532497b499e8b9d45c9bed14
ms.sourcegitcommit: 9e7ceb5604472f3088f611aa0360bd6a716db32b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4022620"
---
# <a name="view-vendor-invoice-automation-results"></a>Wyświetlanie wyników automatyzacji faktur od dostawców

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób wyświetlania stanu faktur od dostawców w zautomatyzowanym procesie przesyłania do przepływu pracy. Szczegóły historii automatyzacji są obsługiwane dla każdej importowanej faktury od dostawcy. W zależności od wykonywanych przez użytkownika procesów biznesowych na stronie **Oczekujące faktury od dostawcy** jest wyświetlana wartość **Stan automatycznego dopasowania odbioru** i **Automatyczne przesyłanie do stanu przepływu pracy**. Istnieje możliwość wyświetlenia szczegółów i utworzenia planu skoncentrowanego na fakturach, które nie wykonały zautomatyzowanego kroku. Po rozwiązaniu tego problemu można wznowić proces zautomatyzowany dla importowanej faktury.

Aby można było edytować przesłaną fakturę, należy wstrzymać automatyczne przetwarzanie. Jeśli faktura w procesie zautomatyzowanego przesyłania do przepływu pracy musi zostać wstrzymana, należy w polu **Uwzględnij w zautomatyzowanym przetwarzaniu** ustaw wartość **Nie** na stronie **Faktury od dostawcy**. Automatyzacja nie zostanie uruchamiana, dopóki w polu **Przetwarzanie automatyczne** nie zostanie ustawiona wartość **Tak**. Dalszą automatyzację faktury można wstrzymać, jeśli jeszcze nie znajduje się w systemie przepływu pracy i nie jest używana przez proces zautomatyzowany.

Jeśli zaimportowana faktura podlega procesowi przesyłania do przepływu pracy”, można wyświetlić wartość **Stan automatyzacji** na stronie **Faktury od dostawcy**. Śledzone są następujące stany:

- **Uwzględnione** — zautomatyzowane procesy zdefiniowane na stronie **Parametry rozrachunków z dostawcami** działają poprawnie, ale nie zostały jeszcze ukończone.
- **Wstrzymane** — wykonywane są zautomatyzowane procesy zdefiniowane na stronie **Parametry rozrachunków z dostawcami** , ale co najmniej jeden krok w procesie nie powiódł się. Stan **Wstrzymane** jest również stosowany, jeśli w polu **Uwzględnij w zautomatyzowanym przetwarzaniu** jest ustawiona wartość **Nie**. Te błędy można wyświetlić, wybierając opcję **Wyświetl ostatnie wyniki**.
- **W przepływie pracy** — zaimportowana faktura została przesłana do systemu przepływu pracy przez zautomatyzowany proces przesyłania do przepływu pracy lub ręcznie.
- **Przepływ pracy ukończony** — ukończono proces przepływu pracy dla zaimportowanej faktury.
