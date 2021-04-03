---
title: Domyślne opisy księgi głównej
description: Opisów domyślnych można użyć do zaktualizowania pola Opis w księgowaniach załączników do księgi głównej.
author: sherry-zheng
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 47c5c9e71dba7a0cb7c798c167208faebeb5af6c
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500387"
---
# <a name="default-descriptions-for-the-general-ledger"></a>Domyślne opisy księgi głównej

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Opisów domyślnych można użyć do zaktualizowania pola **Opis** w księgowaniach załączników do księgi głównej. Ta funkcjonalność została ulepszona tak, aby działała z kosztem dostawy.

Aby skonfigurować domyślne opisy dla księgować w księdze, przejdź do **Administracja organizacyjna \> Konfiguracja \> Domyślne opisy**.

W poniższej tabeli wymieniono nowe wartości, które zostały dodane w polu **Opis** na stronie **Domyślne opisy**, aby obsługiwać koszt dostawy.

| Typ opisu | Notatki |
|---|---|
| Wycena importu — Naliczenie kosztów | Po zaksięgowaniu faktury za zamówienie zakupu naliczony koszt jest przetwarzany w celu oszacowania kosztów podróży. Można określić domyślne opisy, aby dodać numer podróży do opisu. Użyj *%4* jako numeru przesyłki. |
| Wycena importu – zamówienie towaru w drodze | Jeśli jest przetwarzane w drodze, faktura zamówienia zakupu jest księgowana, a towary są księgowane na koncie towarów w drodze. Można określić opisy domyślne, aby dodać numer zamówienia w drodze do opisu. Użyj *%4* dla numeru zamówienia w drodze. |
| Zapasy – Zamknięcie – Korekta | Gdy faktura zobowiązań (AP) jest przetwarzana dla kosztu podróży, przetwarzana jest korekta zapasów w celu oszacowania kosztów podróży. Można określić domyślne opisy, aby dodać numer podróży do opisu. Użyj *%4* jako numeru przesyłki. |

Aby uzyskać więcej informacji na temat pracy ze stroną **Opisy domyślne**, zobacz temat [Konfigurowanie domyślnych opisów dla automatycznego księgowania](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).
