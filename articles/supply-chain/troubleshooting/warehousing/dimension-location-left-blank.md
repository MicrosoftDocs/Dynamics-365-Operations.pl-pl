---
title: Lokalizacja wymiaru nie może być pusta, jeśli ustawiono numer seryjny
description: Jeśli ten błąd występuje podczas potwierdzania wysyłki po utworzeniu zamówienia przeniesienia dla pozycji seryjnej, pole Domyślna lokalizacja przyjęcia jest puste.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6f58c72438d5d1d93e59e46525debd65d44d9a76
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477344"
---
# <a name="error-when-confirming-shipment-after-creating-a-transfer-order-for-a-serial-item"></a>Błąd podczas potwierdzania wysyłki po utworzeniu zamówienia przeniesienia dla pozycji seryjnej

## <a name="symptoms"></a>Objawy

Jeśli utworzysz zlecenie przeniesienia dla pozycji seryjnej przy użyciu magazynu, który obsługuje zaawansowane zarządzanie magazynem (WMS), a następnie po zakończeniu pracy spróbujesz potwierdzić wysyłkę, pojawi się następujący komunikat o błędzie:

> Lokalizacja wymiaru nie może być pusta, jeśli ustawiono numer seryjny wymiaru.

## <a name="cause"></a>Powód

Dzieje się tak, ponieważ pole **Domyślna lokalizacja przychodu** jest puste dla magazynu tranzytowego magazynu „z”.

## <a name="resolution"></a>Rozwiązanie

Aby rozwiązać ten problem, należy określić domyślną lokalizację przychodu w magazynie tranzytowym. Upewnij się, że ta lokalizacja jest kontrolowana za pomocą numeru identyfikacyjnego.
