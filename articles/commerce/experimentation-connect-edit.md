---
title: Łączenie eksperymentu i edytowanie odmian
description: W tym artykule opisano sposób łączenia eksperymentów z usługą innej firmy z systemem Dynamics 365 Commerce i edytowania odmian eksperymentu.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: dcdbd61976402ddd719ece184a86692fbc7c628d
ms.sourcegitcommit: ddcb62bb5fbf26a1178c2bb1aec45a3d2362339e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/07/2022
ms.locfileid: "8942829"
---
# <a name="connect-an-experiment-and-edit-variations"></a>Łączenie eksperymentu i edytowanie odmian

W tym artykule opisano sposób łączenia doświadczenia w Commerce i wprowadzania zmian w odmianach, dzięki czemu są one zgodne z hipotezą. 

Na poniższym diagramie przedstawiono wszystkie kroki związane z konfigurowaniem i przeprowadzaniem eksperymentu na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce. Dodatkowe kroki są zawarte w odrębnych artykułach.

[ ![Proces użytkownika eksperymentu — łączenie i edycja.](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)

Po [skonfigurowaniu eksperymentu](experimentation-setup.md) w usłudze innej firmy nastąpi połączenie eksperymentu w Dynamics 365 Commerce i edycja odmian eksperymentów.

## <a name="connect-your-experiment"></a>Łączenie eksperymentu
Aby połączyć eksperyment, należy uruchomić kreatora **Łączenie eksperymentów**. Kreator przeprowadzi Cię przez kroki wymagane do połączenia eksperymentu. Po zakończeniu pracy kreatora eksperyment jest połączony, a zmiany są tworzone i gotowe do edycji.

Aby rozpocząć Podłączanie doświadczenia w konstruktorze witryn Commerce, należy wykonać następujące kroki.

1. Aby uruchomić kreatora **Połącz eksperyment**, wybierz opcję **Eksperymenty** w lewym okienku nawigacji, a następnie wybierz opcję **Połącz**. Można również uzyskać dostęp do kreatora ze strony lub z edytora fragmentów, edytując go i wybierając na pasku poleceń **Połącz eksperyment**.

    > [!NOTE]
    > - Strona może być połączona tylko z jednym eksperymentem naraz. Aby połączyć stronę z innym eksperymentem, należy najpierw usunąć eksperyment, z którym jest obecnie połączona strona.
    > - Eksperymentować można tylko na stronach z niestandardowym układem. Jeśli strona zawiera wstępnie ustawiony układ, najpierw przekonwertuj go na układ niestandardowy. W tym celu należy przejść na stronę i wybrać polecenie **Konwertuj na niestandardowy układ** na pasku poleceń. Aby uzyskać więcej informacji o układach, zobacz [Ustawienia wstępne i układy niestandardowe](templates-layouts-overview.md#preset-and-custom-layouts). 

1. Jeśli łączysz się z eksperymentem z karty **Eksperymenty** w lewym panelu nawigacyjnym, wybierz nazwę eksperymentu z wyświetlonej listy.
1. Wybierz stronę lub fragment, na którym ma być uruchomiony eksperyment.
1. W ostatnim kroku kreatora wybierz opcję **Wygeneruj odmiany i zakończ kreatora**. Zostaną utworzone odmiany eksperymentu. 

> [!NOTE]
> Aby zaplanować, kiedy eksperyment zostanie opublikowany w działającej witrynie, upewnij się, że zawartość, którą chcesz skojarzyć z eksperymentem, jest dostępna w grupie publikowania *przed* połączeniem eksperymentu. Aby uzyskać więcej informacji o grupach publikacji, zobacz temat [Praca z grupami publikacji](publish-groups.md).

## <a name="edit-your-variations"></a>Edycja odmian

Po wyjściu z kreatora **Połącz eksperyment** tworzone są dla Ciebie warianty. Wykonaj poniższe kroki, aby edytować warianty tak, aby odzwierciedlały wybory, które należy zweryfikować w hipotezie eksperymentu.

1. W widoku edytora za pomocą menu rozwijanego odmiany, znajdującego się pod paskiem poleceń, można edytować każdą odmianę w oparciu o hipotezę oryginalną. Można również określić kontrolę lub zmianę bazową, pozostawiając niezmienioną jedną z odmian.
1. Wybierz moduł do eksperymentowania, wybierz wielokropek (...), a następnie wybierz opcję **Dodaj do eksperymentu**.

> [!NOTE]
> Należy rozważyć ustanowienie zmiany kontrolnej lub podstawowej poprzez pozostawienie jednej ze zmian bez zmian.

## <a name="previous-step"></a>Poprzedni krok
[Konfigurowanie eksperymentu](experimentation-setup.md) 


## <a name="next-step"></a>Następne kroki
[Podgląd i publikowanie eksperymentu](experimentation-preview-publish.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
