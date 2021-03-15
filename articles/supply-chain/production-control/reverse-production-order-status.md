---
title: Wycofywanie stanu zlecenia produkcyjnego
description: W tym temacie opisano sposób wycofania stanu zlecenia produkcyjnego.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdParmStatusDecrease, ProdSetupStatusDecrease
audience: Application User
ms.reviewer: kamaybac
ms.custom: 70131
ms.assetid: b1e0df43-b388-4326-8fb7-501f30c89776
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a73a480eb4ad4ec46f97cb6a4163cb938353a458
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986556"
---
# <a name="reverse-the-production-order-status"></a>Wycofywanie stanu zlecenia produkcyjnego

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób wycofania stanu zlecenia produkcyjnego. 

Wycofanie stanu zlecenia produkcyjnego powoduje cofnięcie zamówienia i wszelkich operacji związanych z marszrutami do poprzedniego etapu cyklu produkcyjnego. Na przykład zlecenie produkcyjne ma stan **zaplanowane**, i zmieniasz stan z powrotem na **Utworzone**. W tym przypadku system musi najpierw zmienić stan na **Oszacowane** znajdujący się bezpośrednio przed stanem **Zaplanowane**. Następnie można zmienić stan na żądany stan — **Utworzone**. **Uwaga:** Zlecenie ze stanem **Zgłoszenie wyrobów gotowych** można cofnąć do wcześniejszego stanu. Jednakże należy ponownie uruchomić Szacowanie i Planowanie operacji, planowanie zadań lub oba typów planowania, aby zaktualizować informacje o zleceniu. Ten krok jest konieczny, ponieważ trzeba również zresetować rezerwacje zużycia pozostałych towarów oraz zużycia zasobów operacyjnych. W pozostałej części tego artykułu wyjaśniono, co się dzieje, gdy wycofujesz stan zlecenia produkcyjnego, korzystając z następujących sposobów:

-   Zmiana stanu z **Oszacowane** na **Utworzone**
-   Zmiana stanu z **Zaplanowane** na **Oszacowane**
-   Zmiana stanu ze **Zwolnione** na **Zaplanowane**
-   Zmiana stanu z **Rozpoczęte** na **Zwolnione**

## <a name="from-estimated-to-created"></a>Zmiana stanu z Oszacowane na Utworzone
W przypadku zmiany stanu zlecenia produkcyjnego z **Oszacowane** na **Utworzone** zużycie towaru obliczone dla pozycji na liście składowej (BOM), zostaje usunięte. Transakcje magazynowe w wierszu produkcji są usuwane, a pole **Następny krok** w wierszach BOM zlecenia produkcyjnego jest zmieniane na **Zakończone**. Gdy zostały zaznaczone opcje **Pochodne zakupy** i **Produkcja pochodna**, wszystkie podległe zamówienia zakupu lub zlecenia produkcyjne są usuwane. Jeśli zostały oszacowane koszty dla zlecenia produkcyjnego lub ręcznie wycofano pozycje, tak aby można było ich użyć w produkcji, transakcje te zostaną usunięte.

## <a name="from-scheduled-to-estimated"></a>Zmiana stanu z Zaplanowane na Oszacowane
Zmiana stanu zlecenia produkcyjnego z **Zaplanowane** na **Oszacowane** powoduje usunięcie zaplanowanych dat rozpoczęcia i zakończenia. Rezerwacje zdolności produkcyjnych wykonane podczas planowania są usuwane, podobnie jak zadania utworzone podczas planowania zadań. Wszystkie zapisane informacje o planowaniu operacji i zadań na stronie **Szczegóły zlecenia produkcyjnego** zostaną usunięte.

## <a name="from-released-to-scheduled"></a>Zmiana stanu ze Zwolnione na Zaplanowane
Zmiana stanu zlecenia produkcyjnego ze **Zwolnione** na **Zaplanowane** powoduje tylko zmianę wartości w polu stanu.

## <a name="from-started-to-released"></a>Zmiana stanu z Rozpoczęte na Zwolnione
Zmiana stanu zlecenia produkcyjnego z **Rozpoczęte** na **Zwolnione** powoduje wycofanie wszystkich pozycji zgłoszonych jako gotowe. Cofane są także ustawienia dotyczące pobranych materiałów oraz dostaw przychodzących i wychodzących. Pole **Następny krok** w wierszach BOM zlecenia produkcyjnego zmieniło się z **Zakończone** na **Zużycie materiału**. Jeśli został zarejestrowany czas lub zgłoszono ilości jako gotowe dla operacji w marszrucie produkcji, ustawienia te zostaną wycofane. Pole **Następny krok** zmieniło się z **Zakończone** na **Zużycie marszruty** w marszrucie produkcji. Ustawienia dla wszystkich elementów, które są księgowane jako „w toku” lub „praca w toku”, zostaną wycofane. Na stronie **Szczegóły zlecenia produkcyjnego** pola wskazujące ilość rozpoczętą lub zgłoszoną jako gotową zostaną zresetowane. Resetowane są również daty dla tych transakcji.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]