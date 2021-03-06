---
title: Rozwiązywanie problemów z uzupełnianiem zapasów
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z uzupełnieniem zapasów w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8940f729e1115405e8d6e50eccc92d9fffe37f3e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828089"
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