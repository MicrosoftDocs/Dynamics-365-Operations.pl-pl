---
title: Dodawanie kanał do hierarchii organizacyjnej
description: W tym artykule opisano, jak dodać kanał do hierarchii organizacyjnej w Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 9def2d7c3cf17ecd9b74ce41f56bc3220a754597
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278605"
---
# <a name="add-a-channel-to-an-organizational-hierarchy"></a>Dodawanie kanał do hierarchii organizacyjnej


[!include [banner](includes/banner.md)]

W tym artykule opisano, jak dodać kanał do hierarchii organizacyjnej w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Kanały muszą być skojarzone z co najmniej jedną hierarchią organizacyjną. Przed utworzeniem kanałów należy upewnić się, że zostały skonfigurowane hierarchie organizacyjne.  

Aby uzyskać więcej informacji na temat tworzenia hierarchii organizacyjnych, należy zapoznać się z [Hierarchie organizacyjne](channels-org-hierarchies.md).

## <a name="select-a-hierarchy"></a>Wybierz hierarchię

Aby wybrać hierarchię, należy wykonać następujące czynności.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Retail i commerce \> Ustawienia kanału \> Hierarchie organizacyjne**.
1. Z listy wybierz hierarchię organizacyjną, do której będzie dodawany kanał.
1. W okienku akcji wybierz opcję **Widok**, aby wyświetlić szczegóły hierarchii.

Poniższy obraz przedstawia szczegóły hierarchii organizacyjnej dla wybranej hierarchii.

![Szczegóły hierarchii organizacyjnej dla wybranej hierarchii.](media/channel-add-to-org-hierarchy-1.png)

## <a name="add-a-channel-to-a-hierachy-node"></a>Dodawanie kanału do węzła hierachy

Aby dodać kanał do węzła hierarchii, wykonaj następujące kroki.

1. Na okienku akcji wybierz opcję **Edytuj**.
1. Wybierz węzeł hierachy, do którego chcesz dodać kanał, a następnie z listy rozwijanej **Wstaw** wybierz opcję **Kanał sprzedaży**. 
1. Wybierz kanał do dodania, a następnie kliknij przycisk **OK**.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. W okienku akcji wybierz opcję **Publikuj** i w przeszłości podaj **Data wejścia w życie** tej akcji, aby ta akcja zaczęła obowiązywać natychmiast.

Poniższy obraz przedstawia sposób wybierania kanału, który ma zostać dodany do węzła hierarchii.

![Wybierz kanał do dodania do węzła hierarchii organizacyjnej.](media/channel-add-to-org-hierarchy-2.png)

Poniższy obraz przedstawia hierarchię z różnymi dodanymi kanałami.

![Hierarchia z różnymi dodanymi kanałami.](media/channel-add-to-org-hierarchy-3.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie kanałów](channels-overview.md)

[Wymagania wstępne dotyczące konfiguracji kanału](channels-prerequisites.md)

[Omówienie organizacji i hierarchii organizacyjnych](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Planowanie hierarchii organizacyjnej](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Hierarchie organizacyjne](channels-org-hierarchies.md)

[Konfigurowanie kanału sprzedaży](channel-setup-retail.md)
    
[Konfigurowanie kanału internetowego](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
