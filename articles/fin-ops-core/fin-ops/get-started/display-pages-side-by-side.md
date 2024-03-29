---
title: Równoległe pokazywanie stron przy użyciu funkcji Otwórz w nowym oknie
description: Ten artykuł zawiera opis sposobu wyświetlania stron obok siebie.
author: jasongre
ms.date: 11/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.openlocfilehash: bfc2aa534da17529421af0a28d1c90ee3aeb40cb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288640"
---
# <a name="show-pages-side-by-side-using-the-open-in-new-window-feature"></a>Równoległe pokazywanie stron przy użyciu funkcji Otwórz w nowym oknie

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Ten artykuł zawiera opis sposobu wyświetlania stron obok siebie.

Może być potrzebne wyświetlenie kilku stron jednocześnie, aby można było szybko wykonać zadanie. Na przykład może być konieczne sprawdzenie poprawności lub wprowadzenie wierszy w kilku arkuszach. Zwykle w celu sprawdzenia poprawności lub wprowadzenia wierszy w kilku arkuszach trzeba przechodzić między stroną z listą arkuszy i stroną zawierającą wiersze dla danego arkusza. Ale dzięki funkcji **Otwórz w nowym oknie** można wyświetlać te strony obok siebie i szybciej wykonywać zadania.

Podczas przeglądania wierszy, kliknij ikonę **Otwórz w nowym oknie**.

[![Kliknij ikonę Otwórz w nowym oknie.](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)

Kliknięcie ikony **Otwórz w nowym oknie** spowoduje wyświetlenie strony wierszy w nowym okienku wyskakującym przeglądarki, a następnie w przeglądarce powrót do strony, na której była wyświetlana lista arkuszy. Możesz wyświetlić obie te strony obok siebie. Po zakończeniu przeglądania arkusza, możesz zmienić wybrany arkusz na stronie arkuszy, a strona wierszy w wyskakującym okienku automatycznie wyświetli wiersze nowo wybranego arkusza.

[![Możesz wyświetlić strony obok siebie.](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)

Dynamiczne łączenie i odświeżanie dokonywane jest z powodu istnienia relacji między danymi źródłowymi tych stron. Jeśli system nie został powiadomiony o relacji między danymi, wyskakujące okienko nie będzie odświeżać się automatycznie w odpowiedzi na zmianę w oknie, z którego to wyskakujące okienko zostało wyświetlone.

Niektóre strony mają wiele widoków, takich jak Widok siatki, Widok nagłówek czy i Widok szczegółów. Ikona **Otwórz w nowym oknie** powoduje, że cała strona otwiera się w nowym oknie przeglądarki. Z tego względu nie można zachować dwóch widoków tej samej strony obok siebie za pomocą funkcji **Otwórz w nowym oknie**. Prawie wszystkie takie strony mają listę nawigacji, której można używać do przełączania między rekordami i wyświetlania podobnego widoku.

Przed rozpoczęciem korzystania z funkcji **Otwórz w nowym oknie** należy tak skonfigurować blokadę wyskakujących okienek w przeglądarce internetowej, aby zezwalać na wyświetlanie wyskakujących okienek z adresu URL witryny. Na przykład można zezwolić na wyświetlanie wyskakujących okienek od „\*.dynamics.com”.

Funkcja **Otwórz w nowym oknie** jest dostępna tylko, gdy więcej niż jedna strona jest otwarta w oknie. Ponadto wyskakujące okienko zostanie automatycznie zamknięte, gdy nie ma więcej otwartych stron (tj. gdy zamkniesz ostatnią stronę w tym oknie). System zamyka również otwarte strony po przejściu do innego obszaru w aplikacji. W związku z tym jeśli masz otwarte wyskakujące okienko i przejdziesz do innego obszaru w aplikacji, wyskakujące okienka są automatycznie zamknięte, ponieważ system zamknął strony w tych oknach.

Górny pasek w wyskakujących okienkach wyświetlają informację o firmie, w której strona została otwarta, i jest tylko do odczytu. Wyskakujące okienko bazuje również na głównym oknie przeglądarki. W przypadku zamknięcia lub odświeżana okna głównego, wszystkie wyskakujące okienka stają się tylko do odczytu. Jeśli tak się stanie, nadal można wyświetlić informacje w tych oknach, ale dane nie są interaktywne.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
