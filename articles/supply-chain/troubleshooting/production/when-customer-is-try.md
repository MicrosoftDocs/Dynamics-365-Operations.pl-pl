---
title: Numer partii jest czyszowany po wybraniu nowego identyfikatora partii
description: Podczas przeglądania wiersza arkusza listy pobrania wartość w polu Numer partii jest czyszowana po wybraniu nowej wartości w polu Identyfikator partii.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: datra
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6d71720b1d3a34a31639db0f829dee300d6f96d53fd61c0a8740be9f2306d6dd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738826"
---
# <a name="batch-number-is-cleared-when-a-new-lot-id-is-selected"></a>Numer partii jest czyszowany po wybraniu nowego identyfikatora partii

Numer artykułu z bazy wiedzy: 4613107

## <a name="symptoms"></a>Objawy

Podczas przeglądania wiersza arkusza listy pobrania wartość w polu **Numer partii** jest czyszowana po wybraniu nowej wartości w polu **Identyfikator partii**.

## <a name="resolution"></a>Rozdzielczość

System jest szybując tak jak zaprojektowany. Zmiana identyfikatora partii umożliwia zmianę kontekstu towaru. W związku z tym numer partii jest resetowany.

Aby skojarzyć numer partii z identyfikatorem partii, musisz najpierw ustawić identyfikator partii.
