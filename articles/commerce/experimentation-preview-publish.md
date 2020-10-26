---
title: Podgląd i publikowanie eksperymentu
description: W tym temacie opisano sposób podglądu i publikowania eksperymentu z Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 91e2e4840a2d53f195d881279050b6415d48b070
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930269"
---
# <a name="preview-and-publish-an-experiment"></a>Podgląd i publikowanie eksperymentu

W tym temacie opisano sposób wyświetlania podglądu i publikowania eksperymentu w Dynamics 365 Commerce po [połączeniu eksperymentu i edytowaniu odmian](experimentation-connect-edit.md). Na poniższym diagramie przedstawiono wszystkie kroki związane z konfigurowaniem i przeprowadzaniem eksperymentu na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce. Dodatkowe kroki są zawarte w odrębnych tematach.

[ ![Proces użytkownika eksperymentu — podgląd i publikowanie](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)

## <a name="preview-your-experiment-variations"></a>Podgląd odmian eksperymentu
Możesz wyświetlić podgląd odmiany i kontynuować ich edycję, dopóki nie będą wyglądać odpowiednio.

1. W konstruktorze witryn należy użyć menu rozwijanego odmiany pod paskiem poleceń, aby wybrać zawartość, której podgląd chcesz wyświetlić. 
1. Wybierz opcję **Podgląd** na górnym pasku. Zostanie wyświetlony podgląd zawartości, taki jak po opublikowaniu.
1. Aby wyświetlić podgląd innej odmiany, wybierz ją z listy rozwijanej odmian i wybierz ponownie **Podgląd**.

## <a name="publish-your-experiment"></a>Publikowanie eksperymentu
Jeśli nie używasz grupy publikowania do planowania, kiedy eksperymenty są aktywne i chcesz publikować natychmiast, wybierz opcję **Publikuj** na pasku poleceń. Wszystkie odmiany należące do eksperymentu zostaną opublikowane.
    
> [!IMPORTANT]
> Jeśli strona zawiera nieopublikowany adres URL, należy najpierw opublikować adres URL inaczej nie będzie widoczny dla użytkowników witryny internetowej. Szczegółowe informacje zawiera temat [Zapisywanie, pogląd i publikowanie strony](save-preview-publish-page.md).
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a>Za pomocą grup publikacji można planować czas uruchomienia eksperymentu
Odmiany utworzone w konstruktorze witryn mogą być planowane do opublikowania za pomocą grupy publikacji. W grupie publikacji można połączyć stronę lub fragment z eksperymentem, przechodząc na kartę**Eksperymenty**, **Strony** lub **Fragmenty**. Aby uzyskać więcej informacji, zobacz temat [Łączenie eksperymentu i edycja odmian](experimentation-connect-edit.md). Aby uzyskać informacje o grupach publikacji, zobacz temat [Praca z grupami publikacji](publish-groups.md).

W przypadku korzystania z grup publikacji z eksperymentami należy pamiętać o pewnych ważnych kwestiach.
- Po dodaniu do grupy publikacji strony lub fragmentu z uruchomionym eksperymentem zostanie on usunięty ze strony lub fragmentu w grupie publikacji.
- Eksperymenty, które są połączone ze stronami w działającej witrynie, nie są dostępne dla stron w grupach publikacji i na odwrót. Podobnie strony, które mają uruchomione eksperymenty w działającej witrynie, nie są dostępne dla innych eksperymentów w grupach publikacji i na odwrót.
- Podczas publikowania lub planowania grupy publikacji cała zawartość w grupie publikacji jest publikowana niezależnie od tego, czy istnieje doświadczenie związane z grupą publikacji.
- Ponieważ grupa publikacji nadal utrzymuje się po opublikowaniu jej w działającej witrynie, eksperymenty z grupy publikacji również będą się utrzymywać. Dlatego nie będzie można kojarzyć innych eksperymentów z tą samą stroną lub fragmentem. Aby uniknąć tego ograniczenia, usuń wszystkie grupy publikacji z trwałymi eksperymentami. Podobnie, jeśli chcesz usunąć eksperyment w działającej witrynie, które istnieje również w grupie publikowania, najpierw usuń go z grupy publikacji.

## <a name="previous-step"></a>Poprzedni krok
[Łączenie i edytowanie eksperymentu](experimentation-connect-edit.md)

## <a name="next-step"></a>Następne kroki
[Uruchamianie i monitorowanie eksperymentu](experimentation-run-monitor.md)
