---
title: Kojarzenie środków trwałych z wynajmami
description: W tym temacie opisano sposób kojarzenia istniejącego środka trwałego z nowym wynajmem.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a0ae7a850ceb13cb41ee5adc406e71105cdad4fe
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712154"
---
# <a name="associate-fixed-assets-with-leases"></a>Kojarzenie środków trwałych z wynajmami

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

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

Jeśli wynajem jest skojarzony ze środkiem trwałym, pole **Okres użytkowania** w księdze środków trwałych zostanie zaktualizowane w celu dostosowania go do najmniejszej wartości z następujących kryteriów: 

 - Okres użyteczności środka trwałego
 - Okres wynajmu ze skojarzonej księgi wynajmu

Jeśli w polu **Przeniesienie własności** jest ustawiona wartość **Tak** dla księgi wynajmu, wartość w polu **Okres użyteczności** zawsze będzie okresem użyteczności środka trwałego. 
 
Okres użyteczności będzie aktualizowany za każdym razem, gdy wynajem zostanie skorygowany, aby zagwarantować amortyzację składnika majątku z prawem do użytkowania w czasie wynajmu, tak jakby był on amortyzowany w przypadku wynajmu środka trwałego.

> [!NOTE]
> Jeśli użytkownik skojarzy środek trwały z wynajmem, przyciski **Amortyzacja środka trwałego** i **Utrata wartości wynajmu** są wyłączone w module Wynajem składnika majątku. Transakcje amortyzacji składnika majątku i utraty wartości wynajmu można wyświetlić w module Środki trwałe. Przycisk **Transakcje składnika majątku**, który powoduje otwarcie formularza kwerendy, również jest wyłączony. Formularz kwerendy **Transakcje składnika majątku** można również otworzyć w module Środki trwałe.  

Na stronach **Środki trwałe** i **Księga środków trwałych** zostanie wyświetlony identyfikator wynajmu skojarzony ze środkami trwałymi. Jeśli środek trwały jest skojarzony z wynajmem, identyfikator wynajmu i opis wynajmu będą wyświetlane na skróconej karcie **Informacje o wynajmie** na stronie **Środki trwałe**. W przypadku ksiąg środków trwałych skojarzonych z księgami wynajmu w polach **Identyfikator wynajmu**, **Opis wynajmu** i **Typ księgi** będą wyświetlane informacje dotyczące wybranej księgi środków trwałych na skróconej karcie **Informacje o wynajmie**, aby wskazać, że jest ona skojarzona z księgą wynajmu.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
