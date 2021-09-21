---
title: Anulowanie reszty dostawy powoduje przeniesienie zamówienia zakupu do stanu Potwierdzone
description: Jeśli reszta dostawy została anulowana w zamówieniu zakupu, w którym jest włączone zarządzanie zmianami, zamówienie zakupu przechodzi do stanu potwierdzonego
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 1d8b331bc5699487dff3491d65daa36293f3212f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477320"
---
# <a name="cancelling-delivery-remainder-moves-purchase-order-to-a-confirmed-state"></a>Anulowanie reszty dostawy powoduje przeniesienie zamówienia zakupu do stanu Potwierdzone

## <a name="symptoms"></a>Objawy

W przypadku zamówienia zakupu, które jest związane z zarządzaniem zmianami, jeśli jedyną żądaną zmianą jest anulowanie reszty dostawy w jednym lub kilku wierszach, zamówienie zakupu będzie przechodzić bezpośrednio do stanu *Potwierdzone*, a arkusz nie zostanie utworzony.

## <a name="resolution"></a>Rozwiązanie

Anulowanie reszty dostawy nie wpływa na zawartość arkusza potwierdzeń. Ta funkcja powinna być używana, gdy wiersz został częściowo odebrany, a pozostała jakość powinna zostać anulowana w kroku procesu po potwierdzeniu zamówienia zakupu u dostawcy.

Jeśli powinno to znaleźć odzwierciedlenie w potwierdzeniu zamówienia, ilość powinna zostać dostosowana w wierszu zamówienia, tak aby potwierdzenie było wymagane. Alternatywnie, jeśli nic nie zostało odebrane w wierszu, ilość może zostać usunięta. W takim przypadku będzie wymagane ponowne potwierdzenie.
