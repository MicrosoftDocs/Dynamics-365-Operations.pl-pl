---
title: Kopiowanie zawartości do innych lokalizacji
description: W tym artykule opisano, jak skopiować istniejącą zawartość do innego locale w obrębie witryny w kreatorze witryn Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 07/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: bcfa3c7cb2ea8018422803d85df6b6761b8d1145
ms.sourcegitcommit: d719d0a549aecac231fad0abb42250eab9dd0ded
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/07/2022
ms.locfileid: "9126455"
---
# <a name="copy-content-to-another-locale"></a>Kopiowanie zawartości do innych lokalizacji

[!include[banner](../includes/banner.md)]

W tym artykule opisano, jak skopiować istniejącą zawartość do innego locale w obrębie witryny w kreatorze witryn Microsoft Dynamics 365 Commerce.

Kiedy tworzysz zawartość w kreatorze stron Commerce, jest ona zawsze powiązana z identyfikatorem lokalizacji, takim jak "en-us". Możesz kopiować poszczególne strony i zasoby do innych lokalizacji w tym samym e-sklepie, zmieniając lokalizację podczas edycji elementu zawartości, a następnie tworząc nowy wariant tego elementu. W niektórych przypadkach, np. gdy wprowadzasz zupełnie nowy region na stronie sklepu, sensowne jest zduplikowanie wszystkich elementów zawartości w istniejącym regionie do nowego regionu. Jeśli nowy locale ma ten sam język podstawowy co jeden z istniejących lokalizacji, możesz użyć istniejącej jako lokalizacji źródłowej dla operacji kopiowania. (Na przykład lokalizacje "en-us" i "en-au" używają języka angielskiego). W ten sposób zmniejszasz wysiłek potrzebny do zlokalizowania zawartości w nowym miejscu.

Poniższe procedury wyjaśniają, jak dodać nowy locale do istniejącego kanału, skopiować wszystkie elementy zawartości z istniejącego locale do nowego locale i monitorować stan operacji kopiowania locale.

## <a name="add-a-new-locale"></a>Dodaj nową lokalizację

Aby dodać nową lokalizację do kreatora witryn Commerce, wykonaj poniższe kroki.

1. Przejdź do swojej witryny w module konstruktora witryn.
1. W okienku nawigacji wybierz pozycję **Ustawienia witryny**, a następnie wybierz opcję **Kanały**.
1. W sekcji **Kanał** wybierz kanał, do którego chcesz dodać nową lokalizację.
1. W oknie dialogowym kanału, które pojawi się po prawej stronie, wybierz **Dodaj lokalizację**.
1. W oknie dialogowym **Dodaj lokalizację**, w polu **Lokale do obsługi** wybierz lokalizację.
1. Sprawdź, czy wartość **Domeny** jest prawidłowa.
1. W polu **ścieżka** wprowadź unikalną ścieżkę URL (na przykład **en-us** lub **english-us**).
1. Kliknij przycisk **OK**.
1. Zamknij okno dialogowe kanału.
1. W sekcji **Kanał** sprawdź, czy nowa lokalizacja znajduje się obok właściwego kanału.
1. Wybierz **Zapisz i opublikuj**.

> [!NOTE]
> Zanim nowa lokalizacja będzie mogła zostać skonfigurowana w programie do budowania witryn, musi zostać dodana do kanału sklepu internetowego w centrali Commerce headquarters.

## <a name="copy-all-content-items-to-a-new-locale"></a>Skopiuj wszystkie elementy zawartości do nowej lokalizacji

Aby skopiować wszystkie elementy zawartości do nowej lokalizacji w kreatorze witryn Commerce, wykonaj poniższe kroki.

1. Przejdź do swojej witryny w module konstruktora witryn.
1. W okienku nawigacji wybierz pozycję **Ustawienia witryny**, a następnie wybierz opcję **Kanały**.
1. Na pasku poleceń wybierz pozycję **Utwórz kopię lokalizacji z**.
1. W oknie dialogowym **Utwórz kopię lokalizacji**, które pojawi się po prawej stronie, w sekcji **Miejsce źródłowe** sprawdź, czy wybrano właściwe miejsce.
1. W polu **Kanał źródłowy** wybierz kanał źródłowy.
1. W polu **Kanał docelowy** wybierz ten kanał źródłowy.
1. W polu **Lokalizacja źródła** wybierz lokalizację źródła.
1. W polu **Lokalizacja docelowa** wybierz nową lokalizację.
1. Wybierz opcję **Kopiuj lokalizację**. Powiadomienie potwierdza, że operacja kopiowania lokalizacji została rozpoczęta.

> [!NOTE]
> Możesz również kopiować treści między różnymi kanałami.

## <a name="monitor-the-status-of-the-locale-copy"></a>Monitorowanie stanu kopii lokalizacji

Aby monitorować stan operacji kopiowania lokalizacji, wykonaj poniższe kroki.

1. Przejdź do swojej witryny w module konstruktora witryn.
1. W okienku nawigacji wybierz pozycję **Ustawienia witryny**, a następnie wybierz opcję **Zadania**.
1. W części **Obecne zadania** wybierz zadanie, które chcesz monitorować. Szczegóły zadania są widoczne w oknie dialogowym wyświetlanym po prawej stronie.
