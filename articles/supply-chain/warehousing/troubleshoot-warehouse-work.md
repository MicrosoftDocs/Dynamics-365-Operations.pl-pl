---
title: Rozwiązywanie problemów pracy magazynowej
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z pracą magazynową w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 3015ec777953cedb5a5d8eea873ed1043cac04cb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970249"
---
# <a name="troubleshoot-warehouse-work"></a>Rozwiązywanie problemów pracy magazynowej

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z pracą magazynową w Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a>Nie można przenieść numerów identyfikacyjnych, które mają pozycje numerów seryjnych, gdy dla grupy wymiarów śledzenia jest dozwolone puste wydanie i puste przyjęcie.

### <a name="issue-description"></a>Opis problemu

Nie można przenieść numeru identyfikacyjnego za pomocą elementu menu **przesunięcia**, jeśli numer seryjny zawiera ustawienia *Dozwolone puste wydanie* i *Dozwolone puste przyjęcie* dla grupy wymiarów śledzenia, i jeśli w tej samej lokalizacji znajduje się wiele numerów identyfikacyjnych, z których niektóre mają numery seryjne, a niektóre ich nie mają.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Ten problem zostanie rozwiązany przez wprowdzane zmiany [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687). Wprowadzenie tych zmian powoduje, że pole **numeru seryjnego** będzie opcjonalne, jeśli są dozwolone puste przyjęcie i pustego wydanie.

## <a name="i-receive-the-following-error-message-in-the-warehouse-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a>W aplikacji magazynu jest zgłaszany następujący komunikat o błędzie podczas przetwarzania przesunięć: „Właściciel zapasów %1 jest niedozwolony w tym procesie”.

### <a name="issue-description"></a>Opis problemu

Brak wymiaru śledzenia **właściciela**, jeśli do tworzenia przesunięć jest używana aplikacja magazynowa. Zwykły arkusz przesunięć zapasów z klienta Supply Chain Management działa zgodnie z oczekiwaniami i może być księgowany tylko wtedy, gdy jest wypełniony wymiar **właściciel**.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji. Obecnie procesy zarządzania magazynem obsługują tylko zapasy będące własnością osoby prawnej.
