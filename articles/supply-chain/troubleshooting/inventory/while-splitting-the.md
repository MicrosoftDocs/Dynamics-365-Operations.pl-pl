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
ms.openlocfilehash: 185365ced5c4516d8fcdbdca88794d0078615888
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026822"
---
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a>Po podziale ilości w ilości catch zamiast ilości nominalnej używana jest ilość minimalna

Numer artykułu z bazy wiedzy: 4612073

## <a name="symptoms"></a>Objawy

W przypadku podziału ilości catch na partie w polu **Ilość pobrania** jest używana minimalna ilość ustawiona dla towaru, a nie ilość nominalna.

## <a name="resolution"></a>Rozdzielczość

System jest szybując tak jak zaprojektowany. Do pobrania system używa konfiguracji minimalnej ilości poszczególnych towarów.
