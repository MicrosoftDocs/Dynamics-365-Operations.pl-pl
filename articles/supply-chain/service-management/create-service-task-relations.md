---
title: Tworzenie relacji zadania serwisowego
description: Zadanie serwisowe można skojarzyć z umowami serwisowymi lub zleceniami serwisowymi, aby opisać zadanie serwisowe, jakie ma zostać wykonane w ramach umowy lub zlecenia.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 9e5fd978c1e9db7e7ce3c06bbeb45b59854f1582
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974667"
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


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]