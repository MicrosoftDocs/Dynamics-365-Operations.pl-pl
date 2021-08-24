---
title: Dodawanie nowej strony witryny
description: W tym temacie opisano, jak dodać nową stronę witryny w Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4b031431499eba0e109ac04dc46ec187250eba694284864bf78bb1f90265d788
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725393"
---
# <a name="add-a-new-site-page"></a>Dodawanie nowej strony witryny

[!include [banner](includes/banner.md)]

W tym temacie opisano, jak dodać nową stronę witryny w Microsoft Dynamics 365 Commerce.

Po utworzeniu szablonów i fragmentów dla witryny następnym krokiem jest rozpoczęcie tworzenia stron, które ich używają. Aby rozpocząć, musisz wybrać szablon lub układ, nazwę strony oraz adres URL strony.

## <a name="template-or-layout"></a>Szablon lub układ

Dla nowej strony można zastosować szablon lub układ. Aby uzyskać więcej informacji, zobacz [Omówienie szablonów i układów](templates-layouts-overview.md).

## <a name="page-name"></a>Nazwa strony

Nazwa strony musi być unikatowa dla danej strony. Powinna ona być opisowa, aby można było łatwo ją odnaleźć i inne osoby wiedziały, że jest przeznaczona dla strony. Należy uważnie wybrać nazwę strony, ponieważ nie można jej później zmienić.

## <a name="page-url"></a>Adres URL strony

Można wybrać opcję wprowadzania adresu URL dla nowej strony. Podczas tworzenia strony można wprowadzić ciąg, który będzie używany do tworzenia pełnego adresu URL. Ten ciąg określany jest jako względny adres URL lub do informacji o adresie URL. Cały adres URL jest następnie generowany na podstawie informacji o adresach URL, a nowa strona jest przypisana do niej. Przed opublikowaniem strony można później zmienić jej adres URL. Aby uzyskać więcej informacji, zobacz temat [Tworzenie adresu URL strony](create-page-URL.md).

> [!NOTE]
> Dynamics 365 Commerce rozdziela adresy URL i zawartość. Innymi słowy, można utworzyć stronę, która nie jest skojarzona z adresem URL i utworzyć adres URL, który nie jest skojarzony ze stroną. W związku z tym może nastąpić założenie zawartości adresu URL i nie wymaga przestoju, a przekierowywanie jest łatwiejsze do zarządzania.

## <a name="add-a-new-page"></a>Dodawanie nowej strony

Aby dodać nową stronę do swojej witryny, wykonaj następujące kroki.

1. W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).
1. Wybierz **Nowa strona**.
1. W oknie dialogowym **Nowa strona** wybierz szablon i wybierz przycisk **OK**.
1. W polu **Nazwa strony** wprowadź nazwę strony (na przykład **Nowa strona**).
1. W polu **adres URL** wprowadź ciąg (adres URL), aby dokończyć adres URL (na przykład **mynewpage**).
1. Kliknij przycisk **OK**. Zostanie wyświetlona strona edytora. Zauważ, że nagłówek i stopka są automatycznie dodawane do strony na podstawie wybranego szablonu.
1. W konspekcie strony wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. Zaznacz element **Kontener** i kliknij przycisk **OK**
1. Wybierz **Kontener płynny**, a następnie wybierz przycisk wielokropka i opcję **Dodaj moduł**.
1. Zaznacz **Blok zawartości sformatowanej**, a następnie kliknij przycisk **OK**.
1. Wybierz **Blok zawartości sformatowanej**, a następnie wybierz przycisk wielokropka i opcję **Dodaj moduł**.
1. Zaznacz **Element bloku zawartości sformatowanej**, a następnie kliknij przycisk **OK**.
1. W okienku właściwości po prawej stronie wybierz pozycję **Akapit**, a następnie w polu wprowadź **Tekst testowy**.
1. Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.
1. W polu **Komentarze** wprowadź **Dodawanie nowej strony**, a następnie kliknij przycisk **OK**.
1. Wybierz opcję **Podgląd**, aby wyświetlić podgląd strony. Po zakończeniu Zamknij kartę podglądu, aby powrócić do narzędzia autorskiego.
1. Wybierz opcję **Publikuj**.
1. W ścieżce nawigacji (struktura nawigacyjna) wybierz firmę **Fabrikam** (lub nazwę witryny).
1. W okienku nawigacji po lewej stronie zaznacz **adresy URL**.
1. Na liście znajdź i zaznacz URL (**mynewpage**).
1. Wybierz opcję **Publikuj**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Modyfikacja istniejącej strony witryny](modify-existing-page.md)

[Wybieranie układów stron](select-page-layouts.md)

[Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania](manage-seo-metadata.md)

[Zapisywanie, pogląd i publikowanie strony](save-preview-publish-page.md)

[Wzbogacanie strony produktu](enrich-product-page.md)

[Wzbogacanie strony docelowej kategorii](enrich-category-page.md)

[Weryfikowanie dostępności zawartości strony](verify-accessibility.md)

[Tworzenie dynamicznych stron handlu elektronicznego na podstawie parametrów adresu URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
