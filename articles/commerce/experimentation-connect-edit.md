---
title: Łączenie eksperymentu i edytowanie odmian
description: W tym temacie opisano sposób łączenia eksperymentów z usługą innej firmy z systemem Dynamics 365 Commerce i edytowania odmian eksperymentu.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 4dbfa96e6393bae6ad4ffa642b39a5d04c596c29
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6349383"
---
# <a name="connect-an-experiment-and-edit-variations"></a>Łączenie eksperymentu i edytowanie odmian

W tym temacie opisano sposób łączenia doświadczenia w Commerce i wprowadzania zmian w odmianach, dzięki czemu są one zgodne z hipotezą. 

Na poniższym diagramie przedstawiono wszystkie kroki związane z konfigurowaniem i przeprowadzaniem eksperymentu na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce. Dodatkowe kroki są zawarte w odrębnych tematach.

[ ![Proces użytkownika eksperymentu — łączenie i edycja.](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)

Po [skonfigurowaniu eksperymentu](experimentation-setup.md) w usłudze innej firmy nastąpi połączenie eksperymentu w Dynamics 365 Commerce i edycja odmian eksperymentów.

## <a name="planning-considerations"></a>Uwagi dotyczące planowania

Przed połączeniem eksperymentu w Commerce trzeba wprowadzić kilka decyzji, które wpływają na sposób zarządzania zawartością przez Commerce.

### <a name="determine-the-scope-of-your-experiment"></a>Określanie zakresu eksperymentu
Po połączeniu eksperymentu zostanie wyświetlony monit o zdefiniowanie zakresu eksperymentu. Eksperymenty są zdefiniowane jako zakres **częściowy** lub **cały**.
- Wybierz opcję **częściowy**, jeśli chcesz przeprowadzić eksperyment na konkretnej części strony. Po wybraniu tej opcji należy określić, które moduły mają być uwzględniane w eksperymencie. Zmiany wprowadzane w częściach domyślnej strony lub fragmentu, które nie są związane z eksperymentem, są automatycznie synchronizowane w różnych odmianach.
- Wybierz opcję **cały**, jeśli chcesz prowadzić eksperyment na całej stronie lub fragmencie. Zostaną utworzone oddzielne kopie domyślnej strony lub fragmentu. Nie trzeba wybierać modułów, które zostaną uwzględnione w eksperymencie, ponieważ cała powierzchnia edycji jest dostępna do zmiany. W razie potrzeby można dodawać, usuwać lub ponownie zamawiać moduły. Jeśli jednak zostaną wprowadzone jakiekolwiek zmiany do strony domyślnej lub fragmentu, z którym jest skojarzona eksperyment, zmiany te muszą być synchronizowane ręcznie we wszystkich odmianach.

<!-- not to editors, we're adding an image here to illustrate the difference. it will help.) -->

> [!NOTE]
> Jeśli użytkownik skojarzy eksperyment ze stroną korzystającą z układu, może wybrać tylko **cały** zakres eksperymentu.

### <a name="decide-if-you-want-to-schedule-when-your-experiment-is-published"></a>Określanie, czy chcesz zaplanować, kiedy eksperyment jest opublikowany
Aby zaplanować, kiedy eksperyment zostanie opublikowany w działającej witrynie, upewnij się, że zawartość, którą chcesz skojarzyć z eksperymentem, jest dostępna w grupie publikowania *przed* połączeniem eksperymentu. 

Aby uzyskać więcej informacji o grupach publikacji, zobacz temat [Praca z grupami publikacji](publish-groups.md).


## <a name="connect-your-experiment"></a>Łączenie eksperymentu
Aby połączyć eksperyment, należy uruchomić kreatora **Łączenie eksperymentów**. Kreator przeprowadzi Cię przez kroki wymagane do połączenia eksperymentu. Po zakończeniu pracy kreatora eksperyment jest połączony, a zmiany są tworzone i gotowe do edycji.

Aby rozpocząć Podłączanie doświadczenia w konstruktorze witryn Commerce, należy wykonać następujące kroki.

1. Aby uruchomić kreatora **Połącz eksperyment**, wybierz opcję **Eksperymenty** w lewym okienku nawigacji, a następnie wybierz opcję **Połącz**. Można również uzyskać dostęp do kreatora ze strony lub z edytora fragmentów, edytując go i wybierając na pasku poleceń **Połącz eksperyment**.

    > [!NOTE]
    > Strona może być połączona tylko z jednym eksperymentem naraz. Aby połączyć stronę z innym eksperymentem, należy najpierw usunąć eksperyment, z którym jest obecnie połączona strona.

1. Wybierz stronę lub fragment, na którym ma być uruchomiony eksperyment.
1. Umożliwia ustawienie zakresu eksperymentów na **częściowy** lub **cały** w zależności od wyboru dokonanego w sekcji [Określ zakres doświadczenia](#determine-the-scope-of-your-experiment) powyżej.
    > [!NOTE]
    > Aby eksperymentować z pełną stroną lub fragmentem, należy włączyć flagę funkcji **Eksperymentowanie ze stronami lub fragmentami**. Aby uzyskać więcej informacji, zobacz temat [Eksperymentowanie w programie Dynamics 365 Commerce](experimentation-overview.md).
    
1. W ostatnim kroku kreatora wybierz opcję **Wygeneruj odmiany i zakończ kreatora**. Zostaną utworzone odmiany eksperymentu. 

## <a name="edit-your-variations"></a>Edycja odmian
Po zamknięciu kreatora zostaną utworzone odmiany. 

Następnie dokonasz edycji odmian, aby odzwierciedlały opcje, które trzeba zweryfikować w hipotezie. Wybierz jedną z poniższych procedur, która odpowiada zakresowi wybranemu dla eksperymentu w powyższej sekcji [Określanie zakresu eksperymentu](#determine-the-scope-of-your-experiment).

### <a name="edit-variations-for-experiments-with-partial-scope"></a>Edycja odmian eksperymentów z częściowym zakresem
Wykonaj poniższe kroki, jeśli w kreatorze **łączenia eksperymentów** został zdefiniowany **częściowy** zakres eksperymentu.

1. W widoku edytora za pomocą menu rozwijanego odmiany, znajdującego się pod paskiem poleceń, można edytować każdą odmianę w oparciu o hipotezę oryginalną. Można również określić kontrolę lub zmianę bazową, pozostawiając niezmienioną jedną z odmian.
1. Wybierz moduł do eksperymentowania, wybierz wielokropek (...), a następnie wybierz opcję **Dodaj do eksperymentu**.

### <a name="edit-variations-for-experiments-with-entire-scope"></a>Edycja odmian eksperymentów z całkowitym zakresem
Jeśli zdefiniowano **całkowity** zakres eksperymentu w kreatorze **Łączenie eksperymentów**, to w widoku edytora należy skorzystać z menu rozwijanego odmiany poniżej paska poleceń, aby edytować poszczególne odmiany na podstawie hipotezy pierwotnej. 

> [!NOTE]
> W każdym przypadku można również określić kontrolę lub zmianę bazową, pozostawiając niezmienioną jedną z odmian.

## <a name="previous-step"></a>Poprzedni krok
[Konfigurowanie eksperymentu](experimentation-setup.md) 


## <a name="next-step"></a>Następne kroki
[Podgląd i publikowanie eksperymentu](experimentation-preview-publish.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]