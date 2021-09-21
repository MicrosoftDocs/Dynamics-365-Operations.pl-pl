---
title: Maksymalny limit umowy zakupu nie obowiązuje dla zapotrzebowania na zakup
description: Maksymalny limit umowy zakupu nie obowiązuje dla zapotrzebowania na zakup
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c19d40dce65acbe80d4572bfc4e925aa87ea4f02
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477286"
---
# <a name="the-purchase-agreement-maximum-limit-isnt-effective-on-a-purchase-requisition"></a>Maksymalny limit umowy zakupu nie obowiązuje dla zapotrzebowania na zakup

## <a name="symptoms"></a>Objawy

Jeśli zapotrzebowanie zakupu jest połączone z umową zakupu, maksymalny limit z umowy zakupu nie obowiązuje w zapotrzebowaniu zakupu. Domyślne informacje o cenie są wprowadzane poprawnie, ale więcej niż maksymalny limit z umowy zakupu może zostać zamówiony w zapotrzebowaniu zakupu.

## <a name="resolution"></a>Rozwiązanie

To zachowanie jest oczekiwane. Zapotrzebowania nie zawsze są zatwierdzane, więc ilość lub kwota nie powinna być rezerwowana w umowie zakupu. Z tego powodu nie będzie można spełnić limitu maksymalnego z umowy zakupu.
