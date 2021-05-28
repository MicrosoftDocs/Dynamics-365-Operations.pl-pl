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
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ccda3bd769a646e2390711883b8e40bec50e4d6a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020990"
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
