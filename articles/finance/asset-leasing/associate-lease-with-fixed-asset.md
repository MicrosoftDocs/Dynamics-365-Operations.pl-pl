---
title: Kojarzenie środków trwałych z wynajmami
description: W tym temacie opisano sposób kojarzenia istniejącego środka trwałego z nowym wynajmem.
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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d627633e43c2e6f5cad90dfe4100ff95a71541f7
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447004"
---
# <a name="associate-fixed-assets-with-leases"></a>Kojarzenie środków trwałych z wynajmami

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób kojarzenia istniejącego środka trwałego z nowym wynajmem. Po skojarzeniu środka trwałego z wynajmem wartość środka trwałego (ROU) w momencie początkowego uznania będzie kosztem nabycia środka trwałego.

Aby można było skojarzyć środek trwały z wynajmem, należy utworzyć rekord dla środka trwałego w module Środki trwałe. Następnie na stronie **Podsumowanie wynajmu** należy utworzyć wynajem i powiązać środek trwały z tym wynajmem.

1. Dodaj wynajem, wykonując kroki w obszarze [Dodaj lub kopiuj wynajmy](add-lease.md). Na stronie **Dodawanie wynajmu** w polu **Numer środka trwałego** wybierz środek trwały, który nie został jeszcze nabyty.
2. Wybierz opcję **Księgi** i potwierdź harmonogram płatności.
3. Wybierz **Początkowe uznanie**.
4. Wybierz **Arkusz wynajmu składnika majątku**.

    Początkowy wpis w arkuszu uznania dla wynajmu obciąża środek trwały na kwotę, która zwykle jest księgowana po stronie debetowej konta składnika majątku z PDU.

    Teraz można wyświetlić typ transakcji i księgę dla środka trwałego.

5. Wybierz **Szczegóły arkusza**.
6. Wybierz opcję **Wiersze**, aby wyświetlić poszczególne wiersze danego wpisu w arkuszu.
7. Wybierz wiersz arkusza zawierający środek trwały, a następnie wybierz kartę **Środki trwałe**.

    Na karcie **Środki trwałe** wyświetlany jest typ transakcji oraz księga. Domyślnie pole **Typ transakcji** jest ustawione na **Nabycie**, a pole **Księga** ma ustawioną bieżącą księgę dla środka trwałego.

Po zaksięgowaniu wpisu w arkuszu początkowego uznania transakcja jest wyświetlana jako transakcja nabycia dla środka trwałego. Aby wyświetlić tabelę transakcji, należy przejść do **Środki trwałe \> Środki trwałe \> Środki trwałe**, wybrać odpowiedni środek trwały i wybrać pozycję **Wyceny**. Powinno być widoczne, że początkowe uznanie wpisu w arkuszu utworzyło transakcję nabycia dla danego środka trwałego.

Środek trwały może teraz zostać zamortyzowany przy użyciu standardowych funkcji amortyzacji w module Środki trwałe. Aby uzyskać więcej informacji na temat amortyzacji, zobacz [Metody i konwencje amortyzacji środka trwałego](../fixed-assets/depreciation-methods-conventions.md).

> [!NOTE]
> Jeśli użytkownik skojarzy środek trwały z wynajmem, przyciski **Amortyzacja środka trwałego** i **Utrata wartości wynajmu** są wyłączone w module Wynajem składnika majątku. Transakcje amortyzacji składnika majątku i utraty wartości wynajmu można wyświetlić w module Środki trwałe. Przycisk **Transakcje składnika majątku**, który powoduje otwarcie formularza kwerendy, również jest wyłączony. Formularz kwerendy **Transakcje składnika majątku** można również otworzyć w module Środki trwałe.  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]