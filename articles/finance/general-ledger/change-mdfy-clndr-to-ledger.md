---
title: Zmienianie lub ponowne przypisywanie kalendarza księgi
description: W tym artykule opisano sposób zmiany kalendarza aktualnie przypisanego do księgi oraz przypisania nowego kalendarza do księgi.
author: kweekley
ms.date: 05/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-07
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 751954e0dc5f682b99ab7fe349cd505dc9da7858
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848614"
---
# <a name="change-or-reassign-a-ledger-calendar"></a>Zmienianie lub ponowne przypisywanie kalendarza księgi

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób zmiany kalendarza aktualnie przypisanego do księgi oraz przypisania nowego kalendarza do księgi.

## <a name="issue"></a>Problem

Zdarza się, że firmy muszą zmienić istniejący kalendarz przypisany do księgi lub przypisać nowy kalendarz.

## <a name="resolution"></a>Rozwiązanie

Istnieją dwa scenariusze zmiany lub ponownego przypisania kalendarza księgi. Pierwszy scenariusz obejmuje zmianę istniejącego kalendarza, który jest już przypisany do księgi. Drugi scenariusz obejmuje utworzenie nowego kalendarza i przypisanie go do księgi. Obie zmiany można wprowadzić w dowolnym momencie, nawet po zaksięgowaniu transakcji w księdze.

### <a name="change-an-existing-fiscal-calendar"></a>Zmiana istniejącego kalendarza obrachunkowego

Aby zmienić istniejący kalendarz przypisany do księgi, wybierz kolejno opcje **Księga główna \> Ustawienia księgi \> Księga** i wybierz łącze do kalendarza obrachunkowego, aby otworzyć stronę **Kalendarze księgi**.

Istnieją ograniczenia dotyczące zmian, które można wprowadzać w kalendarzu. Można na przykład zmieniać daty rozpoczęcia i zakończenia *okresów* w roku, ale nie można zmieniać dat rozpoczęcia i zakończenia *roku* w kalendarzu.

Aby zmienić okresy w roku, wybierz odpowiedni kalendarz i rok. Najpierw użyj przycisku **Usuń okres**, aby usunąć niektóre lub wszystkie istniejące okresy operacyjne. Można usunąć wszystkie okresy operacyjne z wyjątkiem pierwszego. Następnie użyj przycisku **Podziel okres**, aby podzielić pozostały okres lub okresy na nowe okresy, wprowadzając odpowiednią datę rozpoczęcia dla następnego okresu.

Po zmianie okresów w kalendarzu należy uruchomić proces **Ponownie oblicz okresy księgi** dla każdej firmy, do której jest przypisany kalendarz. Chociaż żaden komunikat ostrzegawczy nie przypomina o ukończeniu tego kroku, proces ponownego obliczenia jest wymagany w celu zaktualizowania okresu przypisanego do każdej zaksięgowanej transakcji w księdze głównej. Aby uruchomić proces ponownego obliczania, wybierz opcję **Ponownie oblicz okresy księgi** na stronie **Ustawienia księgi** w każdej firmie.

Jeśli proces ponownego obliczania nie zostanie uruchomiony, salda transakcji bilansu próbnego lub sprawozdań finansowych mogą zostać nieprawidłowo uwzględnione w okresach. W takim przypadku salda można poprawić w dowolnym momencie, uruchamiając proces ponownego obliczania.

### <a name="assign-a-new-fiscal-calendar"></a>Przypisywanie nowego kalendarza obrachunkowego

Aby przypisać nowy kalendarz obrachunkowy, wybierz kolejno pozycje **Księga główna \> Ustawienia księgi \> Księga** i wybierz opcję **Edytuj**, aby przełączyć stronę **Księga** w tryb edycji. Następnie w polu **Kalendarz obrachunkowy** wybierz nowy kalendarz obrachunkowy.

Po zmianie kalendarza obrachunkowego księgi należy uruchomić proces **Ponownie oblicz okresy księgi**. Podczas przypisywania nowego kalendarza obrachunkowego do księgi zostanie wyświetlony komunikat przypominający o ukończeniu tego kroku. Treść komunikatu może sugerować, że proces ponownego obliczania jest opcjonalny, ale tak nie jest. Jego przeprowadzenie jest konieczne w celu aktualizacji okresu przypisanego do każdej transakcji zaksięgowanej w księdze głównej. Aby uruchomić proces ponownego obliczania, wybierz opcję **Ponownie oblicz okresy księgi** na stronie **Ustawienia księgi**.

Jeśli proces ponownego obliczania nie zostanie uruchomiony, salda transakcji bilansu próbnego lub sprawozdań finansowych mogą zostać nieprawidłowo uwzględnione w okresach. W takim przypadku salda można poprawić w dowolnym momencie, uruchamiając proces ponownego obliczania.
