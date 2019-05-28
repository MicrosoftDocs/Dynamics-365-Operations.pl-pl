---
title: Równoległe pokazywanie stron przy użyciu funkcji Otwórz w nowym oknie
description: Ten artykuł zawiera opis sposobu wyświetlania stron obok siebie w Microsoft Dynamics 365 for Finance and Operations.
author: aneesmsft
manager: AnnBe
ms.date: 09/07/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df9b091735a4971446c5b5d0e054076260040683
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558959"
---
# <a name="show-pages-side-by-side-by-using-the-open-in-new-window-feature"></a>Równoległe pokazywanie stron przy użyciu funkcji Otwórz w nowym oknie

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera opis sposobu wyświetlania stron obok siebie w Microsoft Dynamics 365 for Finance and Operations.

Microsoft Dynamics 365 for Finance and Operations ułatwia efektywne wykonywanie zadań. W niektórych przypadkach może być potrzebne wyświetlenie kliku stron jednocześnie, aby szybko wykonać zadanie. Na przykład może być konieczne sprawdzenie poprawności lub wprowadzenie wierszy w kilku arkuszach. Zwykle w tym celu trzeba przechodzić między stroną z listą arkuszy i stroną zawierającą wiersze dla danego arkusza. Ale dzięki funkcji **Otwórz w nowym oknie** można wyświetlać te strony obok siebie i szybciej wykonywać zadania.

Podczas przeglądania wierszy, kliknij ikonę **Otwórz w nowym oknie**.

[![open-in-new-window-icon](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)

Kliknięcie ikony **Otwórz w nowym oknie** spowoduje wyświetlenie strony wierszy w nowym okienku wyskakującym przeglądarki, a następnie w przeglądarce powrót do strony, na której była wyświetlana lista arkuszy. Możesz wyświetlić obie te strony obok siebie. Po zakończeniu przeglądania arkusza, możesz zmienić wybrany arkusz na stronie arkuszy, a strona wierszy w wyskakującym okienku automatycznie wyświetli wiersze nowo wybranego arkusza.

[![pages-show-side-by-side](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)

Dynamiczne łączenie i odświeżanie dokonywane jest z powodu istnienia relacji między danymi źródłowymi tych stron. Jeśli system nie został powiadomiony o relacji między danymi, wyskakujące okienko nie będzie odświeżać się automatycznie w odpowiedzi na zmianę w oknie, z którego to wyskakujące okienko zostało wyświetlone.

Niektóre strony mają wiele widoków, takich jak Widok siatki, Widok nagłówek czy i Widok szczegółów. Ikona **Otwórz w nowym oknie** powoduje, że cała strona otwiera się w nowym oknie przeglądarki. Z tego względu nie można zachować dwóch widoków tej samej strony obok siebie za pomocą funkcji **Otwórz w nowym oknie**. Jednak prawie wszystkie takie strony mają listę nawigacji, której można używać do przełączania między rekordami i wyświetlania podobnego widoku.

Przed rozpoczęciem korzystania z funkcji **Otwórz w nowym oknie** należy tak skonfigurować blokadę wyskakujących okienek w przeglądarce, aby zezwalać na wyświetlanie wyskakujących okienek z adresu URL witryny programu Finance and Operations. Na przykład można zezwolić na wyświetlanie wyskakujących okienek od „\*.dynamics.com”.

Funkcja **Otwórz w nowym oknie** jest dostępna tylko, gdy więcej niż jedna strona jest otwarta w oknie. Ponadto wyskakujące okienko zostanie automatycznie zamknięte, gdy nie ma więcej otwartych stron (tj. gdy ostatnia strona w tym oknie zostanie zamknięta). Program Finance and Operations zamyka również otwarte strony po przejściu do innego obszaru w aplikacji. W związku z tym jeśli masz otwarte wyskakujące okienko i przejdziesz do innego obszaru w aplikacji, wyskakujące okienka są automatycznie zamknięte, ponieważ strony w tych oknach zostały zamknięte przez system.

Górny pasek w wyskakujących okienkach wyświetlają informację o firmie, w której strona została otwarta, i jest tylko do odczytu. Wyskakujące okienko opiera się również na głównym oknie przeglądarki programu Finance and Operations. W przypadku zamknięcia lub odświeżana okna głównego, wszystkie wyskakujące okienka stają się tylko do odczytu. Oznacza to, że nadal można wyświetlić informacje w tych oknach, ale dane nie są interaktywne.
