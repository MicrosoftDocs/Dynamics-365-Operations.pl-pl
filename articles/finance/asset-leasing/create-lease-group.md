---
title: Tworzenie grupy wynajmu
description: W tym temacie opisano sposób konfigurowania grup wynajmu. Grupy wynajmu są wymagane do tworzenia nowych wynajmów.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
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
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e8ad226e87776615d9c19a239e0fb90b648d9c49
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210464"
---
# <a name="create-a-lease-group"></a>Tworzenie grupy wynajmu

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób konfigurowania grup wynajmu. Grupy wynajmu są wymagane do tworzenia nowych wynajmów. Księgi wynajmu są skojarzone z każdą grupą wynajmu. Księgi wynajmu decydują o domyślnych księgach, które muszą zostać utworzone dla każdego wynajmu. Określone konta można przypisać do grupy wynajmu na stronie **Parametry księgowania wynajmu**.

## <a name="create-a-lease-book-and-add-a-lease-group"></a>Tworzenie książki wynajmu i dodawanie grupy wynajmu

1. Przejdź do **Wynajem składnika majątku \> Ustawienia \> Grupy wynajmu**.
2. W okienku akcji wybierz opcję **Nowe**, aby dodać grupę wynajmu. Wiersz zostanie dodany do siatki.
3. W nowym wierszu w polu **Grupa wynajmu** wprowadź wartość.
4. W polu **Opis** wprowadź lub wybierz wartość.

Wprowadzone informacje zostaną dodane do pola **Grupa wynajmu** na stronie **Dodaj wynajem**.

## <a name="associate-a-book-with-a-lease-group"></a>Kojarzenie księgi z grupą wynajmu

Po utworzeniu grup wynajmu można przypisać księgi do każdej grupy. Podczas tworzenia wynajmu i przypisywania jej do grupy wynajmu system tworzy zestaw harmonogramów dla każdej księgi skojarzonej z daną grupą wynajmu.

> [!NOTE]
> Aby można było przypisać księgi do grupy wynajmu, należy je skonfigurować.

1. Przejdź do **Wynajem składnika majątku \> Ustawienia \> Grupa wynajmu**.
2. Wybierz grupę wynajmu, a następnie wybierz opcję **Księgi**.
3. Wybierz opcję **Nowy**, a następnie w polu **Typ księgi** wybierz księgę, która ma zostać przypisana do grupy wynajmu. Można przypisać wiele ksiąg do grupy wynajmu, jeśli wynajem musi być księgowany na różne sposoby.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]