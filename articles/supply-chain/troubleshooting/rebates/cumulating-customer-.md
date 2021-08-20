---
title: Kumulacja rabatów dla odbiorcy nie powiedzie się, gdy używane są grupy rabatowe dla pozycji
description: W przypadku użycia umów rabatowych z klientem w połączeniu z grupami rabatowymi dla towarów rabaty są obliczane, ale kumulacja nie powiedzie się.
author: sherry-zheng
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PdsRebateTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: fc3381dab77cf80c0fd65f3bc27c11b814e72368631bd0e2145aac0be4f4fba4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760377"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a>Kumulacja rabatów dla odbiorcy nie powiedzie się, gdy używane są grupy rabatowe dla pozycji

Numer artykułu z bazy wiedzy: 4611372

## <a name="symptoms"></a>Objawy

W przypadku użycia umów rabatowych z klientem (typów *kwota*)  w połączeniu z grupami rabatowymi dla towarów rabaty są obliczane, ale kumulacja nie powiedzie się.

## <a name="resolution"></a>Rozdzielczość

System jest szybując tak jak zaprojektowany. Grupy pozycji grupuje tylko pozycje, które mają ten sam warunek progu. Warunek rabatu (próg) jest ustawiany w stosunku do kwoty dla każdego towaru, a nie z skumulowanej kwoty dla jakiegokolwiek towaru w grupie towarów.
