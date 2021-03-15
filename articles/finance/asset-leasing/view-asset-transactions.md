---
title: Wyświetlanie zobowiązania, składnika majątku i transakcji wydatków
description: W tym temacie opisano sposób wyświetlania transakcji dla wynajętego składnika majątku. Transakcje te obejmują transakcje zobowiązań z tytułu wynajmu i transakcje wydatków wykonawczych, które zostały zaksięgowane.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 76c7eff17df92b01317544112099e391fd05d105
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995375"
---
# <a name="view-liability-asset-and-expense-transactions"></a>Wyświetlanie zobowiązania, składnika majątku i transakcji wydatków

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób wyświetlania transakcji dla wynajętego składnika majątku. Transakcje te obejmują transakcje zobowiązań z tytułu wynajmu i transakcje wydatków wykonawczych, które zostały zaksięgowane. Wartości bilansowe zobowiązania i składnika majątku z prawem do użytkowania (PDU) są wykorzystywane w kilku raportach. Służą one również do obliczania wartości korekt.

## <a name="liability-transactions"></a>Transakcje zobowiązań

Aby wyświetlić transakcje zobowiązań z tytułu wynajmu, wybierz umowę wynajmu na stronie **Podsumowanie wynajmu**, a następnie wybierz opcję **Księgi**, aby otworzyć księgi dołączone do rekordu wynajmu. Po zaksięgowaniu początkowego ujęcia, faktury lub arkusza odsetek wybierz opcję **Transakcje zobowiązań**.

Na stronie **Transakcje zobowiązań** są wyświetlane transakcje zwiększające lub zmniejszające zobowiązanie z tytułu wynajmu. Kwoty ujemne na tej stronie reprezentują transakcje uznaniowe w standardowej aplikacji. Wszelkie naliczenia odsetek są pokazywane jako wartości ujemne i zwiększają łączne zobowiązanie z tytułu wynajmu. Wszelkie korekty wynajmu są wyświetlane jako wartości dodatnie lub ujemne, w zależności od charakteru i wpływu księgi wynajmu. Bieżące całkowite saldo netto zobowiązania z tytułu wynajmu dla wybranej umowy wynajmu jest wyświetlane w lewej dolnej części strony.

## <a name="asset-transactions"></a>Transakcje składnika majątku

Aby wyświetlić transakcje należności z tytułu wynajmu, wybierz umowę wynajmu na stronie **Podsumowanie wynajmu**, a następnie wybierz opcję **Księgi**, aby otworzyć księgi wynajmu dołączone do rekordu wynajmu. Następnie wybierz opcję **Transakcje składnika majątku**.

Na stronie **Transakcja składnika majątku** są wyświetlane transakcje, które powodują zwiększenie lub zmniejszenie należności z tytułu wynajmu i wartości na kontach umorzenia. Obciążenia są pokazywane jako wartości dodatnie, a uznania jako wartości ujemne, podobnie jak na stronie **Transakcje zobowiązań**. Zaksięgowane początkowe ujęcie i późniejsze umorzenie są wyświetlane w dolnej lewej części strony jako saldo środka składnika majątku. 

## <a name="expenses-transactions"></a>Transakcje wydatkowe

Aby wyświetlić transakcje wydatków z tytułu wynajmu, wybierz umowę wynajmu na stronie **Podsumowanie wynajmu**, a następnie wybierz opcję **Księgi**, aby otworzyć księgi wynajmu dołączone do rekordu wynajmu. Następnie wybierz opcję **Transakcje wydatkowe**.

Na stronie **Transakcje wydatkowe** są wyświetlane wszystkie wydatki, które zostały zaksięgowane dla wynajmu, takie jak koszty odsetek, wydatki amortyzacji i wszelkie koszty wykonawcze.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]