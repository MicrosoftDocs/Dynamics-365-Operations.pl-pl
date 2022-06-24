---
title: Szablony serwisów
description: Można zdefiniować umowę serwisową jako szablon, tak aby później można było kopiować wiersze z tego szablonu do innej umowy serwisowej lub zlecenia serwisowego.
author: sorenva
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7c99e56751230a7b8881dc55c1d460674cc6f0c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850504"
---
# <a name="service-templates"></a>Szablony serwisów

[!include [banner](../includes/banner.md)]

Można zdefiniować umowę serwisową jako szablon, tak aby później można było kopiować wiersze z tego szablonu do innej umowy serwisowej lub zlecenia serwisowego.

## <a name="example"></a>Przykład

Klient korzystający z usług danej firmy ma identyczne podnośniki serwisowe w pięciu różnych miejscach.

Trzeba skonfigurować pięć umów serwisowych dla tego klienta, po jednej dla każego miejsca.
Aby zmniejszyć ilość pracy polegającej na powtarzaniu tych samych czynności i aby mieć pewność, że dane konfiguracyjne są identyczne we wszystkich umowach serwisowych, trzeba utworzyć umowę serwisową i zdefiniować ją jako szablon dla prac serwisowych związanych z podnośnikami.

Następnie można skopiować wiersze szablonu do pięciu nowych umów serwisowych, wypełniając je danymi z formularza.

## <a name="create-a-template"></a>Utwórz szablon

Podczas tworzenia szablonu serwisu trzeba utworzyć umowę serwisową oraz wymagane wiersze w tej umowie, a następnie powiązać tę umowę z grupą szablonów serwisów.

> [!NOTE]
> Umowa serwisowa może zostać zdefiniowana jako szablon tylko wtedy, gdy nie są z nią powiązane żadne zlecenia serwisowe. Z kolei nie można wygenerować zleceń serwisowych dla umowy serwisowej zdefiniowanej jako szablon.

## <a name="copy-template-lines"></a>Kopiuj wiersze szablonu

Wiersze szablonu serwisu można skopiować do innej umowy serwisowej lub do zlecenia serwisowego.

Podczas kopiowania wierszy szablonu do zleceń serwisowych lub do umów serwisowych grupy szablonów są wyświetlane w postaci drzewa, w którym można rozwijać każdą grupę. W ten sposób moża wyświetlić każy szablon i wiersz szablonu.

Łatwiej jest określić wiersze szablonu serwisu, które mają zostać skopiowane, gdy szablony zostaną pogrupowane przy użyciu nazw odzwierciedlających przeznaczenie szablonów.

## <a name="related-articles"></a>Powiązane artykuły

[Kopiowanie wierszy szablonów serwisu](copy-service-template-lines.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]