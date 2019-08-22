---
title: Składniki majątku i zlecenia pracy
description: W tym temacie opisano składniki majątku i zlecenia pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bd55988578be2b0287b399549f17642bfb1693b
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783512"
---
# <a name="assets-and-work-orders"></a>Składniki majątku i zlecenia pracy

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

W tym temacie opisano składniki majątku i zlecenia pracy w module Zarządzanie składnikami majątku. Składniki majątku i zlecenia pracy są centralnymi częściami modułu Zarządzanie składnikami majątku. *Składnik majątku* jest maszyną lub częścią maszyny, która wymaga ciągłej konserwacji i serwisowania. Składniki majątku mogą być tworzone w strukturze hierarchicznej i mogą być powiązane z lokalizacjami czynności konserwacyjnych. Zadania konserwacji mogą być planowane na wszystkich poziomach struktury składników majątku.

Dla każdego składnika majątku są skonfigurowane różne dane, takie jak informacje o produkcie i specyfikacja składnika majątku oraz wymagane plany konserwacji. Poniższa ilustracja przedstawia omówienie danych o składnikach majątku i przynależności składników majątku do typów zadań. Czerwony tekst jest używany dla przykładów, które pokazują dziedziczenie i zależności.

![Rysunek 1](media/05-overview-image.png)

Każde zlecenie pracy ma typ zlecenia, np. konserwacja zapobiegawcza, konserwacja naprawcza lub inspekcja. Zlecenie pracy zawiera jedno lub więcej zadań zlecenia pracy. Każde zadanie zlecenia pracy definiuje zadanie, które należy wykonać na składniku majątku i pokrewnym typie zadania. Przykłady powiązanych typów stanowisk obejmują remont po 10 000 km, 50 000 km, 1 roku oraz inspekcję bezpieczeństwa. Jedno zlecenie pracy może być powiązane z wieloma składnikami majątku.

Na poniższej ilustracji przedstawiono omówienie kluczowych danych w zleceniu pracy.

![Rysunek 2](media/06-overview-image.png)

Zlecenie pracy może być powiązane z innym zamówieniem pracy, a typy zadań mogą zawierać kolejne zadania, tworzące zlecenie pracy. Ogólnie, nie istnieją żadne zależności między zleceniami pracy. Dzięki temu mogą one zmienić swój stan cyklu życia zlecenia pracy i mogą być planowane niezależnie od siebie.

Zlecenia pracy mogą być tworzone na różne sposoby, które odnoszą się do konserwacji korekcyjnej, zapobiegawczej lub reaktywnej. Można także ręcznie tworzyć zlecenia pracy. Na poniższej ilustracji przedstawiono omówienie procesu automatycznego lub ręcznego tworzenia zleceń pracy.

![Rysunek 3](media/07-overview-image.png)

Aby zaplanować i uruchomić zadanie konserwacji w zleceniu pracy, należy wykonać kilka czynności. Na poniższej ilustracji przedstawiono omówienie przetwarzania w zleceniu pracy.

![Rysunek 4](media/08-overview-image.png)

> [!NOTE]
> Generalnie w trakcie pracy w Microsoft Dynamics 365 for Finance and Operations i module **Zarządzania składnikami majątku** wybierz opcję **Nowy**, aby utworzyć nowy rekord, wybierz **Edytuj**, aby zaktualizować istniejący rekord, a następnie wybierz **Zapisz**, aby zapisać nowy lub edytować dane.
