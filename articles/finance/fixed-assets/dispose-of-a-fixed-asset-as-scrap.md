---
title: Likwidacja środków trwałych uznanych za odpadki
description: W tym temacie opisano proces eliminowania transakcji dla środka trwałego, który został zlikwidowany jako odpadki.
author: moaamer
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 20f5fe0f8f2654df5027c363ebf5922f8344d928
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5241129"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a>Likwidacja środków trwałych uznanych za odpadki

[!include [banner](../includes/banner.md)]

W tym temacie opisano proces eliminowania transakcji dla środka trwałego, który został zlikwidowany jako odpadki. Typy transakcji, które można wyeliminować, obejmują transakcje nabycia i skumulowanej amortyzacji środka trwałego oraz inne transakcje środków trwałych. Eliminacja tych transakcji wpływa na konta arkuszy bilansowych, takie jak korekta nabycia, korekta amortyzacji, przeszacowanie, zmniejszenie wartości i konta zmniejszenia wartości.

| Transakcja                                         | Debet (Dr.) | Kredyt (Cr.) |
|-----------------------------------------------------|-------------|--------------|
| Dr. Umorzenie                        | X           |              |
| Cr. Zysk/strata z tytułu środków trwałych                          |             | X            |
| Dr. Zysk/strata z tytułu środków trwałych                          | X           |              |
| Cr. Konto księgowania nabycia środka trwałego                 |             | X            |
| Dr. Zysk/strata z tytułu środków trwałych (wartość księgowa netto \[NBV\]) | X           |              |
| Cr. Zysk/strata z tytułu środków trwałych (NBV)                    |             | X            |

> [!NOTE]
> Zalecamy ścisłą pracę z głównym oficerem finansowym firmy lub kontrolerem w celu zidentyfikowania prawidłowych kont, które powinny być używane dla poszczególnych typów transakcji, a także sprawdzenia, czy proces likwidacji i transakcje, które generuje aktualizują te konta poprawnie.

Przed usunięciem środka trwałego jako odpadki należy utworzyć konta księgowe skojarzone z wartością nabycia środka trwałego, amortyzację dla bieżącego roku, amortyzację w latach ubiegłych oraz NBV środka trwałego. Typy transakcji środków trwałych są wyświetlane na stronie **Profile księgowania środków trwałych**. Przejdź do **Środki twałe \> Ustawienia \> Profile księgowania środków trwałych**, a następnie w skróconej karcie **Likwidacja** wybierz opcję **Odpadki** w polu powyżej siatki. Poniższa ilustracja przedstawia listę typów transakcji środków trwałych na stronie **Profile księgowania środków trwałych**.


[![Likwidacja składnika majątki jako odpadków, rys. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)

W poniższym przykładzie środek trwały został nabyty 1 stycznia 2018 r. i zostanie uznany za odpadki w dniu 31 marca 2019 r.

- **Cena nabycia:** 24 000,00 dolarów amerykańskich (USD)
- **Okres użytkowania:** Dwa lata
- **Metoda amortyzacji:** Liniowy okres użytkowania
- **Kwota amortyzacji:** 1 000,00 dolarów amerykańskich miesięcznie

Kwota NBV środka trwałego jest obliczana przy użyciu następującej formuły:

Wartość księgowa netto = Cena nabycia - Amortyzacja

W tym przykładzie środek trwały został nabyty i został zamortyzowany w ciągu 15 miesięcy od stycznia 2018 r. do marca 2019 r. Dlatego NBV składnika majatku jest 9 000,00 USD (24 000,00 USD – 15 000,00 USD).

[![Przykład amortyzacji środków trwałych](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)


Aby utworzyć arkusz likwidacji, należy przejść do **Środki trwałe \> Wpisy w arkuszu \> Arkusz środków trwałych**, a następnie w okienku akcji wybrać **Wiersze**. Wybierz **Likwidacja — odpadki**, a następnie wybierz identyfikator środka trwałego. Aby w pełni usunąć środek trwały, nie wprowadzaj wartości w polach **Debet** lub **Kredyt**.

[![Arkusz środków trwałych](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)

Transakcja likwidacji środków trwałych zmienia wartości pól dla księgi środków trwałych w następujący sposób:

- W sekcji **Saldo** pole **Stan** jest aktualizowane na **Uznany za odpadki**.
- W sekcji **Rozchód** w polu **Data likwidacji** jest ustawiana data uznania środka trwałego za odpadki.

[![Szczegóły arkusza środków trwałych](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)

Na poniższej ilustracji przedstawiono saldo środka trwałego.

[![Saldo środka trwałego](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)

Poniższa ilustracja przedstawia zaksięgowany załącznik.

[![Wartość księgowa netto](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]