---
title: Tworzenie relacji zadania serwisowego
description: Zadanie serwisowe można skojarzyć z umowami serwisowymi lub zleceniami serwisowymi, aby opisać zadanie serwisowe, jakie ma zostać wykonane w ramach umowy lub zlecenia.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed0800c4a650233190c6a33b1690790f0e2bf051
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814105"
---
# <a name="create-service-task-relations"></a>Tworzenie relacji zadania serwisowego    

[!include [banner](../includes/banner.md)]

Zadanie serwisowe można skojarzyć z umowami serwisowymi lub zleceniami serwisowymi, aby opisać zadanie serwisowe, jakie ma zostać wykonane w ramach umowy lub zlecenia. Te informacje są dostępne dla serwisantów i klientów.

## <a name="create-a-relation-with-a-service-agreement"></a>Tworzenie relacji z umową serwisową

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.

2.  Wybierz istniejącą umowę serwisową lub utwórz nową.

3.  W okienku akcji kliknij przycisk **Zadania serwisowe**.

4.  W formularzu **Zadania serwisowe** naciśnij kombinację klawiszy CTRL+N, aby utworzyć nowy wiersz, a następnie wybierz zadanie serwisowe z listy **Zadania serwisowe**, aby je dołączyć do umowy serwisowej.

5.  Na karcie **Opis** wprowadź w polach tekstowych dowolne opisowe notatki wewnętrzne lub zewnętrzne.

6.  Zamknij formularz, aby zapisać rekord.

Powtarzaj tę procedurę do chwili utworzenia wszystkich wymaganych relacji zadań serwisowych dla umowy serwisowej. Pozwala to na określenie zadań serwisowych w dołączonych wierszach umowy.

Relacja zadań serwisowych utworzona dla umowy serwisowej jest dostępna z poziomu wszystkich zleceń serwisowych dołączonych do umowy serwisowej.

## <a name="create-a-relation-with-a-service-order"></a>Tworzenie relacji ze zleceniem serwisowym

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.

2.  Wybierz istniejące zlecenie serwisowe lub utwórz nowe.

3.  W okienku akcji kliknij przycisk **Zadania serwisowe**.

4.  W formularzu **Zadania serwisowe** naciśnij kombinację klawiszy CTRL+N, aby utworzyć nowy wiersz, a następnie wybierz zadanie serwisowe z listy **Zadania serwisowe**, aby je dołączyć do zlecenia serwisowego.

5.  Na karcie **Opis** wprowadź w polach tekstowych dowolne opisowe notatki wewnętrzne lub zewnętrzne.

6.  Zamknij formularz, aby zapisać rekord.

Powtarzaj tę procedurę do chwili utworzenia wszystkich wymaganych relacji zadań serwisowych dla zlecenia serwisowego. Pozwala to na wybranie zadania serwisowego, dla którego utworzono relację podczas tworzenia wierszy zlecenia serwisowego.

Relacje zadań serwisowych tworzone dla zlecenia serwisowego są dostępne z poziomu określonego zlecenia serwisowego.

## <a name="see-also"></a>Informacje dodatkowe

[Omówienie zadań serwisowych](service-tasks.md)


  


