---
title: Tworzenie relacji zadania serwisowego
description: Zadanie serwisowe można skojarzyć z umowami serwisowymi lub zleceniami serwisowymi, aby opisać zadanie serwisowe, jakie ma zostać wykonane w ramach umowy lub zlecenia.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f9a7808357916ed80ddfa46e1e4f362e0dde1671
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819071"
---
# <a name="create-service-task-relations"></a>Tworzenie relacji zadania serwisowego    

[!include [banner](../includes/banner.md)]

Zadanie serwisowe można skojarzyć z umowami serwisowymi lub zleceniami serwisowymi, aby opisać zadanie serwisowe, jakie ma zostać wykonane w ramach umowy lub zlecenia. Te informacje są dostępne dla serwisantów i klientów.

## <a name="create-a-relation-with-a-service-agreement"></a>Tworzenie relacji z umową serwisową

1.  Przejdź do **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.

2.  Wybierz istniejącą umowę serwisową lub utwórz nową.

3.  W okienku akcji wybierz przycisk **Zadania serwisowe**.

4.  W formularzu **Zadania serwisowe** wybierz **Nowy**, aby utworzyć nowy wiersz, a następnie wybierz zadanie serwisowe z listy **Zadania serwisowe**, aby je dołączyć do umowy serwisowej.

5.  Na karcie **Opis** wprowadź w polach tekstowych dowolne opisowe notatki wewnętrzne lub zewnętrzne.

6.  Zamknij formularz, aby zapisać rekord.

Powtarzaj tę procedurę do chwili utworzenia wszystkich wymaganych relacji zadań serwisowych dla umowy serwisowej. Pozwala to na określenie zadań serwisowych w dołączonych wierszach umowy.

Relacja zadań serwisowych utworzona dla umowy serwisowej jest dostępna z poziomu wszystkich zleceń serwisowych dołączonych do umowy serwisowej.

## <a name="create-a-relation-with-a-service-order"></a>Tworzenie relacji ze zleceniem serwisowym

1.  Przejdź do **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.

2.  Wybierz istniejące zlecenie serwisowe lub utwórz nowe.

3.  W okienku akcji wybierz przycisk **Zadania serwisowe**.

4.  W formularzu **Zadania serwisowe** wybierz **Nowy**, aby utworzyć nowy wiersz, a następnie wybierz zadanie serwisowe z listy **Zadania serwisowe**, aby je dołączyć do zlecenia serwisowego.

5.  Na karcie **Opis** wprowadź w polach tekstowych dowolne opisowe notatki wewnętrzne lub zewnętrzne.

6.  Zamknij formularz, aby zapisać rekord.

Powtarzaj tę procedurę do chwili utworzenia wszystkich wymaganych relacji zadań serwisowych dla zlecenia serwisowego. Pozwala to na wybranie zadania serwisowego, dla którego utworzono relację podczas tworzenia wierszy zlecenia serwisowego.

Relacje zadań serwisowych tworzone dla zlecenia serwisowego są dostępne z poziomu określonego zlecenia serwisowego.

## <a name="see-also"></a>Informacje dodatkowe

[Omówienie zadań serwisowych](service-tasks.md)


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]