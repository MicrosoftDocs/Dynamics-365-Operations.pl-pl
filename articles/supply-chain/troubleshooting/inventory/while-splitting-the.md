---
title: Po podziale ilości w ilości catch zamiast ilości nominalnej używana jest ilość minimalna
description: W przypadku podziału ilości catch na partie w polu Ilość pobrania jest używana minimalna ilość ustawiona dla towaru, a nie ilość nominalna.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 424ad46281612f6a3e8cb4c90478a39f757d5416c3ce1d77ed6ff6dba7b20dcb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723462"
---
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a>Po podziale ilości w ilości catch zamiast ilości nominalnej używana jest ilość minimalna

Numer artykułu z bazy wiedzy: 4612073

## <a name="symptoms"></a>Objawy

W przypadku podziału ilości catch na partie w polu **Ilość pobrania** jest używana minimalna ilość ustawiona dla towaru, a nie ilość nominalna.

## <a name="resolution"></a>Rozdzielczość

System jest szybując tak jak zaprojektowany. Do pobrania system używa konfiguracji minimalnej ilości poszczególnych towarów.
