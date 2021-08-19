---
title: Nie można zastosować szablonu do zwolnionego produktu
description: Nie można zastosować szablonu do zwolnionego produktu.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 566686b6a86e67c87f75f9f2e397592174d3d749034f18997ca8ce651c2594a2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760401"
---
# <a name="you-cant-apply-a-template-to-create-a-released-product"></a>Nie możesz zastosować szablonu, aby utworzyć zwolniony produkt

Numer artykułu z bazy wiedzy: 4612097

## <a name="symptoms"></a>Objawy

Podczas tworzenia nowego zwolnionego produktu przy użyciu okna dialogowego **Nowy zwolniony produkt** można wybrać szablon. Szablon powinien dostarczać domyślne ustawienia wielu pól nowego zwolnionego produktu. Jednak niektóre lub wszystkie pola nie są ustawiane po wybraniu szablonu.

## <a name="cause"></a>Powód

Wiele stron w firmie Microsoft Dynamics 365 Supply Chain Management umożliwia utworzenie szablonu, który określa początkowe ustawienia rekordów wyświetlanych na tych stronach. Można utworzyć jeden z tych szablonów, wybierając pozycję **Informacje o rekordzie** na karcie **Opcje** w okienku akcji. Jednak zwolnione produkty są o wiele bardziej złożone niż większość innych typów rekordów. Chociaż można wybrać **informacje o rekordzie** na stronie **Zwolnione produkty**, aby utworzyć szablon, i chociaż można wybrać ten szablon podczas tworzenia zwolnionego produktu, szablon nie będzie dostarczał oczekiwanych wartości pól dla nowego zwolnionego produktu. W związku z tym nie można używać szablonów „informacji o rekordzie” dla zwolnionych produktów. Zamiast tego trzeba utworzyć dedykowane szablony produktów.

## <a name="resolution"></a>Rozdzielczość

Aby utworzyć szablon produktu, należy użyć menu **Szablon** na karcie **Produkt** w okienku akcji, a nie przycisku **Informacje o rekordzie** na karcie **Opcje**.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. W okienku akcji, na karcie **Produkt** w grupie **Nowy** wybierz pozycję **Szablon**, a następnie wybierz opcję **Utwórz szablon osobisty** lub **Utwórz szablon udostępniony** zgodnie z potrzebą.
