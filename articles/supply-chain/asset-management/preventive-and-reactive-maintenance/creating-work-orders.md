---
title: Tworzenie zlecenia pracy
description: W tym temacie opisano tworzenie zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0a348bc9b7f5a24c5a3ac57113d430a92020b893
ms.sourcegitcommit: 6476f27c8d3dced7c2e9a7344a4e378b51a1983e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/27/2019
ms.locfileid: "1922121"
---
# <a name="creating-work-orders"></a>Tworzenie zlecenia pracy

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

W przypadku zaplanowanych zadań konserwacji zapobiegania następnym krokiem jest utworzenie zleceń pracy dla tych zadań. Można to zrobić w jednym z harmonogramów konserwacji: Zaplanowane zadania w harmonogramie konserwacji mogą mieć różne typy odwołań:

| Typ odwołania | Opis                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| Plany konserwacji     | Zadania profilaktycznej konserwacji oparte na planie konserwacji typu „czas” lub „licznik”                       |
| Serie czynności konserwacyjnych    | Zadania profilaktycznej obsługi technicznej zawierające kilka składników majątku, które wymagają podobnego typu obsługi.           |
| Żądanie konserwacji   | Ręcznie utworzone żądanie konserwacji lub naprawy składnika majątku, które może zostać przekształcone w zlecenie pracy. |


1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Wszystkie harmonogramy konserwacji** lub **Otwieranie wierszy harmonogramu konserwacji** lub **Otwieranie puli harmonogramów konserwacji**.

2. Wybierz zaplanowane zadania konserwacyjne, dla których chcesz utworzyć zlecenie prac i kliknij pozycję **Zlecenie pracy**. W okienku dialogowym **Tworzenie zlecenia pracy** łączna liczba godzin prognozowanych dla wybranych wierszy jest wyświetlana w polu **Godziny prognozy konserwacji**.

3. W sekcji **Parametry** wybierz liczbę zleceń pracy, które mają zostać utworzone. Istnieje możliwość utworzenia jednego zlecenia pracy dla wiersza harmonogramu konserwacji lub szeregu zleceń pracy na podstawie wybranych opcji w sekcji **Jedno zlecenie pracy na**.

4. Wybierz **Typ zlecenia pracy**, który będzie używany we wszystkich tworzonych zleceniach pracy. Na poniższej ilustracji przedstawiono przykład okna dialogowego **Tworzenie zlecenia pracy**.

![Rysunek 1](media/18-preventive-maintenance.png)

5. Kliknij przycisk **OK**. Utworzono co najmniej jedno zlecenie pracy.

