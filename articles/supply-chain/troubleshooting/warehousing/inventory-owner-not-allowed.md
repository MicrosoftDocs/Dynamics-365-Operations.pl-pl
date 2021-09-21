---
title: Właściciel zapasów jest niedozwolony podczas przetwarzania przeniesień
description: 'Możesz zobaczyć komunikat o błędzie: „Właściciel zapasów %1 jest niedozwolony”. Procesy zarządzania magazynem obsługują tylko zapasy będące własnością osoby prawnej.'
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4ee29cfc7bad990cd1ee5deaa98fca217af772ed
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477284"
---
# <a name="inventory-owner-not-allowed-when-processing-movements-in-the-warehouse-app"></a>Właściciel zapasów jest niedozwolony podczas przetwarzania przeniesień w aplikacji magazynu

## <a name="symptoms"></a>Objawy

Podczas przetwarzania przemieszczeń w aplikacji mobilnej Warehouse Management może zostać wyświetlony następujący komunikat o błędzie:

> Właściciel zapasów %1 jest niedozwolony w tym procesie.

## <a name="cause"></a>Powód

Dzieje się tak, ponieważ brakuje wymiaru śledzenia **Właściciel**, jeśli do tworzenia przeniesień jest używana aplikacja Warehouse Management. Zwykły arkusz przesunięć zapasów z klienta Supply Chain Management działa zgodnie z oczekiwaniami i może być księgowany tylko wtedy, gdy jest wypełniony wymiar **właściciel**.

## <a name="resolution"></a>Rozwiązanie

Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji. Obecnie procesy zarządzania magazynem obsługują tylko zapasy będące własnością osoby prawnej.
