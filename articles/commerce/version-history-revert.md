---
title: Wyświetlanie historii wersji w celu przywracania stron i fragmentów
description: W tym artykule opisano, jak wyświetlić historię wersji strony lub fragmentu i przywrócić starszą wersję w konstruktorze witryny Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 06/21/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: c4d78103a3c08ee4052290fccf6750aba7eecf4a
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2022
ms.locfileid: "9474107"
---
# <a name="view-version-history-to-revert-pages-and-fragments"></a>Wyświetlanie historii wersji w celu przywracania stron i fragmentów

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak wyświetlić historię wersji strony lub fragmentu i przywrócić starszą wersję w konstruktorze witryny Microsoft Dynamics 365 Commerce.

Konstruktor stron Commerce umożliwia przeglądanie historii wersji strony lub fragmentu i w razie potrzeby powrót do określonej wcześniejszej wersji dokumentu. Gdy dokument jest otwarty, możesz wybrać polecenie **Pokaż historię** na pasku poleceń, aby otworzyć okno dialogowe **Historia wersji**, w którym na karcie **Wersja** znajduje się historia wszystkich wersji i działań związanych z zapisywaniem dla danej strony lub fragmentu. Możesz wtedy wybrać poprzednią wersję dokumentu z listy, wyświetlić jej podgląd i przywrócić ją jako aktualną wersję. Zakładka **Aktywność** okna dialogowego zawiera pełną historię aktywności dokumentu, w tym wszystkie zdarzenia zapisywania, publikowania i nieopublikowania.

> [!NOTE]
> Nowa wersja dokumentu jest tworzona za każdym razem, gdy autor strony wprowadzi zmiany, a następnie wybierze opcję **Zakończono edycję** dla dokumentu. 

Aby wyświetlić historię wersji strony lub fragmentu i powrócić do poprzedniej wersji, wykonaj następujące kroki.

1. W programie do budowania witryn otwórz stronę lub fragment, dla którego chcesz wyświetlić historię wersji.
1. Na pasku poleceń wybierz opcję **Pokaż historię**.

    ![Przycisk Pokaż historię.](./media/version-history-1.png)

1. W oknie dialogowym **Historia wersji**, na karcie **Wersja**, wybierz poprzednią wersję dokumentu. W okienku właściwości po prawej stronie znajduje się miniaturka podglądu wybranej wersji oraz informacje o tym, kto i kiedy ją zmodyfikował.

    ![Widok listy historii wersji.](./media/version-history-2.png)

1. Aby wyświetlić w pełni renderowany podgląd wybranej wersji dokumentu, wybierz opcję **Podgląd**. Aby zamknąć podgląd i wrócić do okna dialogowego **Historia wersji**, wybierz **Zakończ podgląd**.
1. Aby przywrócić poprzednią wersję dokumentu, wybierz go z listy na karcie **Wersja**, a następnie wybierz pozycję **Przywróć**. Zostanie wyświetlone okno komunikatu **Przywróć wersję \<version number\>** z prośbą o potwierdzenie czynności przywracania. 

    ![Przycisk przywracania i okno wiadomości z potwierdzeniem.](./media/version-history-3.png)

1. Aby kontynuować akcję przywracania, wybierz pozycję **Przywróć**. Konstruktor strony zostaje odświeżony i pokazuje przywróconą wersję strony lub fragmentu.
1. Aby opublikować przywróconą wersję, wybierz pozycję **Zakończ edycję**, a następnie wybierz pozycję **Publikuj**, aby opublikować fragment strony.
