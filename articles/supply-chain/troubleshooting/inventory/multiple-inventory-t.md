---
title: Wiele transakcji magazynowych dla numerów partii, gdy aktualizacja fizyczna jest wyłączona
description: Po skorygowaniu wiersza zamówienia zakupu dla towarów, dla których w opcji Aktualizacji fizycznej w grupie numerów partii ustawiono wartość Nie, tworzona jest wiele transakcji magazynowych.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventNumGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1fa54cdfdbc5608fb6c7114dced0f96bab47253e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026827"
---
# <a name="multiple-inventory-transactions-for-batch-numbers-when-on-physical-update-is-disabled"></a>Wiele transakcji magazynowych dla numerów partii, gdy aktualizacja fizyczna jest wyłączona

Numer artykułu z bazy wiedzy: 4613390

## <a name="symptoms"></a>Objawy

Po skorygowaniu wiersza zamówienia zakupu dla towarów, dla których w opcji **Aktualizacji fizycznej** w grupie numerów partii ustawiono wartość *Nie*, tworzona jest wiele transakcji magazynowych.

W przypadku tworzenia towaru, dla którego dla opcji **Aktualizacji fizycznej** w grupie numerów partii jest ustawiona wartość *Nie*, system automatycznie utworzy nowy numer partii w przypadku zmodyfikowania ilości w wierszu zakupu i zapisania strony zamówienia zakupu.

## <a name="resolution"></a>Rozdzielczość

Ustawienie **Przy fizycznej aktualizacji** dla grup numerów partii działa następująco:

- Gdy jest ustawiona wartość *Tak*, nowe numery partii są tworzone tylko po fizycznej aktualizacji (na przykład przy wysłaniu lub otrzymaniu towaru).
- Gdy jest ustawiona wartość *Nie*, nowy numer partii jest tworzony za każdym razem, gdy stosowana jest aktualizacja (na przykład przy dodaniu nowej ilości do zamówienia zakupu).
