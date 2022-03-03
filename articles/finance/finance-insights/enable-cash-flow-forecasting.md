---
title: Włączanie prognozowania przepływów pieniężnych
description: W tym temacie wyjaśniono, jak włączyć funkcję prognozowania przepływów pieniężnych w Finance Insights.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 763818f70095964d77ff82cf02178367d05eaf23
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109586"
---
# <a name="enable-cash-flow-forecasting"></a>Włączanie prognozowania przepływów pieniężnych

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak włączyć funkcję prognozowania przepływów pieniężnych w Finance Insights.

> [!NOTE]
> Aby skorzystać z prognoz płatności w przepływie pieniężnym, należy skonfigurować funkcję przewidywania płatności odbiorcy w sposób opisany w temacie [Włączanie prognoz płatności odbiorcy](enable-cust-paymnt-prediction.md).
  
1. Otwórz obszar roboczy **Zarządzanie funkcjami** i wykonaj następujące kroki:

    1. Wybierz **Sprawdź, czy są aktualizacje**.
    2. Na karcie **Wszystko** wyszukaj **prognozy przepływów pieniężnych**. Jeśli nie znajdziesz tej funkcji, wyszukaj **(Podgląd) Prognozy przepływów pieniężnych**. 
    3. Włączanie funkcji.

2. Przejdź do **Zarządzanie gotówką i bankami \> Ustawienia prognozy przepływów pieniężnych**, a następnie dodaj konta płynności, które powinny zostać uwzględnione w prognozach. Należy również skonfigurować konto płynności dla płatności na kartach **Rozrachunki z odbiorcami** i **Rozrachunki z dostawcami**. Pamiętaj, aby ponownie przeliczyć prognozę przepływów pieniężnych.

    > [!NOTE]
    > Jeśli konta płynności nie są skonfigurowane, nie można wygenerować przepływu pieniężnego.
    >
    > Więcej informacji na temat uruchamiania Prognozy przepływów pieniężnych znajdziesz: [Prognozy przepływów pieniężnych](../cash-bank-management/cash-flow-forecasting.md).

3. Przejdź do **Zarządzanie gotówką i bankami \> Ustawienia \> Finance Insights (wersja zapoznawcza) \> Prognozy przepływów pieniężnych (wersja zapoznawcza)**, a następnie wykonaj następujące kroki:

    1. Na karcie **Prognoza przepływów pieniężnych** wybierz opcję **Włącz funkcję**.
    2. Wybierz opcję **Utwórz model przewidywania**.

> [!NOTE]
> Trening modelu **Prognoza przepływów pieniężnych** wymaga danych zawierających co najmniej 100 transakcji obejmujących ponad rok. Zaleca się, aby mieć co najmniej dwa lata z ponad 1000 transakcji.

Więcej informacji na temat funkcji prognozowania przepływów pieniężnych znajdziesz: [Prognozy przepływów pieniężnych](cash-flow-forecast-intro.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
