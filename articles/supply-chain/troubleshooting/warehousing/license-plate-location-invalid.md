---
title: Błąd nieprawidłowego numeru identyfikacyjnego lub lokalizacji w aplikacji mobilnej
description: Podczas skanowania identyfikatora numeru identyfikacyjnego lub lokalizacji może pojawić się błąd wskazujący, że jest on nieprawidłowy. Upewnij się, że identyfikator numeru identyfikacyjnego nie jest zarezerwowany na coś innego.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: f9f10dbade0d13b8fc4b0fc92981d84e6e28e83e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477359"
---
# <a name="invalid-license-plate-or-location-error-when-scanning-in-the-mobile-app"></a>Błąd nieprawidłowego numeru identyfikacyjnego lub lokalizacji podczas skanowania numeru identyfikacyjnego w aplikacji mobilnej

## <a name="symptoms"></a>Objawy

Podczas skanowania identyfikatora numeru identyfikacyjnego lub lokalizacji może pojawić się następujący komunikat o błędzie:

> Numer identyfikacyjny lub lokalizacja jest nieprawidłowa.

## <a name="resolution"></a>Rozwiązanie

Upewnij się, że identyfikator numeru identyfikacyjnego nie jest zarezerwowany na coś innego. Ten problem występuje, jeśli wartość, którą użytkownik przeskanował w aplikacji Warehouse Management, była zarówno prawidłową lokalizacją, jak i prawidłowym identyfikatorem numeru identyfikacyjnego. Jednak ten problem został rozwiązany w wersji 10.0.11.
