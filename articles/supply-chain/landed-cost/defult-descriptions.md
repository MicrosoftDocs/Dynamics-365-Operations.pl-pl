---
title: Domyślne opisy księgi głównej
description: Opisów domyślnych można użyć do zaktualizowania pola Opis w księgowaniach załączników do księgi głównej.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: f95dff3a77a552d5788d813b3d13dc30579be715
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695715"
---
# <a name="default-descriptions-for-the-general-ledger"></a>Domyślne opisy księgi głównej

[!include [banner](../../includes/banner.md)]

Opisów domyślnych można użyć do zaktualizowania pola **Opis** w księgowaniach załączników do księgi głównej. Ta funkcjonalność została ulepszona tak, aby działała z kosztem dostawy.

Aby skonfigurować domyślne opisy dla księgować w księdze, przejdź do **Administracja organizacyjna \> Konfiguracja \> Domyślne opisy**.

W poniższej tabeli wymieniono nowe wartości, które zostały dodane w polu **Opis** na stronie **Domyślne opisy**, aby obsługiwać koszt dostawy.

| Typ opisu | Notatki |
|---|---|
| Wycena importu — Naliczenie kosztów | Po zaksięgowaniu faktury za zamówienie zakupu naliczony koszt jest przetwarzany w celu oszacowania kosztów podróży. Można określić domyślne opisy, aby dodać numer podróży do opisu. Użyj *%4* jako numeru przesyłki. |
| Wycena importu – zamówienie towaru w drodze | Jeśli jest przetwarzane w drodze, faktura zamówienia zakupu jest księgowana, a towary są księgowane na koncie towarów w drodze. Można określić opisy domyślne, aby dodać numer zamówienia w drodze do opisu. Użyj *%4* dla numeru zamówienia w drodze. |
| Zapasy – Zamknięcie – Korekta | Gdy faktura zobowiązań (AP) jest przetwarzana dla kosztu podróży, przetwarzana jest korekta zapasów w celu oszacowania kosztów podróży. Można określić domyślne opisy, aby dodać numer podróży do opisu. Użyj *%4* jako numeru przesyłki. |

Aby uzyskać więcej informacji na temat pracy ze stroną **Opisy domyślne**, zobacz temat [Konfigurowanie domyślnych opisów dla automatycznego księgowania](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).
