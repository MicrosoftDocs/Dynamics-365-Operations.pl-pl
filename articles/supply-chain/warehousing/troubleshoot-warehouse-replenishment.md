---
title: Rozwiązywanie problemów z uzupełnianiem zapasów
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z uzupełnieniem zapasów w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7748a18d2b6f612b3ac9ac1a75efb6ae5f13859a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993900"
---
# <a name="troubleshoot-warehouse-replenishment"></a>Rozwiązywanie problemów z uzupełnianiem zapasów

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z uzupełnieniem zapasów w Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a>Otrzymuję następujący komunikat o błędzie: „Praca %1 nie może zostać odblokowana, ponieważ zawiera niedokończone prace uzupełniające”.

### <a name="issue-description"></a>Opis problemu

Praca pobrania została zablokowana z powodu zależnej pracy uzupełniania zapasów.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

W przypadku użycia grupy czynności uzupełnienia popytu, jeśli lokalizacja pobrania musi być uzupełniana w celu zrealizowania zapotrzebowania zamówienia źródłowego, system tworzy zarówno pracę uzupełniającą, jak i pracę pobrania. Jednak system blokuje pracę pobrania do momentu zakończenia pracy uzupełniania. To zachowanie jest celowe, ponieważ lokalizacja pobrania nie ma wystarczającej ilości zapasów, dopóki praca uzupełniania zapasów nie zostanie zakończona. Zakończ pracę uzupełniania zapasów, a następnie przetwórz pracę pobrania.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]