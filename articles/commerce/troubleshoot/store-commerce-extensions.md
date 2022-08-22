---
title: Rozwiązywanie problemów z rozszerzeniem Store Commerce
description: W tym artykule opisano sposób rozwiązywania problemów z rozszerzeniem aplikacji Microsoft Dynamics 365 Commerce Store Commerce.
author: josaw1
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 1a2d6a68b7556d8b4d05529efd90f9e66f0c5925
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269789"
---
# <a name="troubleshoot-store-commerce-extension-issues"></a>Rozwiązywanie problemów z rozszerzeniem Store Commerce

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób rozwiązywania problemów z rozszerzeniem aplikacji Microsoft Dynamics 365 Commerce Store Commerce.

## <a name="extensions-packages-arent-loaded"></a>Pakiety rozszerzeń nie są załadowane

### <a name="extensions-packages-dont-appear-on-the-pos--settings-page"></a>Pakiety rozszerzeń nie są widoczne na stronie POS \> Ustawienia

Wyzwalacze środowiska uruchomieniowego Commerce Runtime (CRT) mogły nie zostać zaktualizowane, aby uwzględnić pakiet rozszerzeń, lub nie zostały wdrożone. Aby uzyskać więcej informacji, zobacz [Możliwości i wyzwalacze Commerce runtime (CRT)](../dev-itpro/commerce-runtime-extensibility-trigger.md).

### <a name="extensions-packages-appear-on-the-pos--settings-page-but-the-manifest-isnt-loaded"></a>Pakiety rozszerzeń pojawiają się na stronie POS \> Ustawienia, ale manifest nie jest ładowany

Potwierdź, że pakiety rozszerzeń istnieją w folderze **C:\\Program Files\\Microsoft Dynamics 365\\10.0\\Store Commerce\\Rozszerzenia**. Jeśli pakiety istnieją, powinien istnieć folder **POS** zawierający manifest.

Jeśli nie ma folderu **POS**, upewnij się, że projekt Store Commerce poprawnie odwołuje się do projektu rozszerzenia punkt sprzedaży (POS). Sprawdź poprawność ścieżki odwołania do projektu i upewnij się, że istnieje. 

Na poniższej przykładowej ilustracji projekt instalatora ma problemy z tym projektem rozszerzenia, do których istnieje odwołanie.

![Odwołanie do projektu Instalatora Store Commerce jest nieprawidłowe.](media/ReferenceNotValid.png)

Jeśli odwołanie do projektu rozszerzenia zostanie poprawnie dodane, w projekcie instalatora nie będzie żadnego problemu z ostrzeżeniem ani zależnością, jak pokazano na poniższej przykładowej ilustracji.

![Odwołanie do projektu Instalatora Store Commerce jest prawidłowe.](media/ReferenceValid.png)
