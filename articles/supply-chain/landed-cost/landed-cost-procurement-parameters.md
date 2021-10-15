---
title: Parametry dotyczące zamówień i zaopatrzenia dla kosztu dostawy
description: W tym temacie opisano, jak skonfigurować odpowiednie parametry zaopatrzenia i zaopatrzenia w przypadku korzystania z modułu kosztów dostawy.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: cb41fc6477acb005912c735a691de6d1a659c020
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569848"
---
# <a name="procurement-and-sourcing-parameters-for-landed-cost"></a>Parametry dotyczące zamówień i zaopatrzenia dla kosztu dostawy

[!include [banner](../../includes/banner.md)]

Strona **Parametry modułu Zaopatrzenie i sourcing** zawiera kilka ustawień, które są szczególnie istotne podczas korzystania z modułu **Koszty dostawy**. Użyj okna dialogowego **Aktualizacja wierszy zamówienia**, które jest otwarte ze strony **Parametry zaopatrzenia i sourcingu**, aby określić, czy wiersze zamówienia zakupu mają być automatycznie aktualizowane po w nagłówku zamówienia zakupu

Aby zakończyć tę konfigurację, należy wykonać następujące czynności.

1. Przejdź do **Zaopatrzenie i sourcing \> ustawień \> Parametry modułu Zaopatrzenie i sourcing**.
1. Na karcie **Ogólne** zaznacz łącze **Aktualizuj wiersze zamówienia**.
1. W oknie dialogowym **Aktualizacja wierszy zamówienia** znajduje się lista pól w nagłówku zamówienia, które mogą być także automatycznie aktualizowane w powiązanych polach w wierszach zamówienia. Dla każdego pola na liście można ustawić jedną z następujących wartości:

    - **Zawsze** – Wiersze zamówienia powinny być automatycznie aktualizowane po zaktualizowaniu nagłówka zamówienia.
    - **Nigdy** – Wiersze zamówienia nigdy nie powinny być aktualizowane po zaktualizowaniu nagłówka zamówienia.
    - **Monituj** — użytkownik będzie monitowany o wybranie, czy wiersze zamówienia powinny być aktualizowane.
