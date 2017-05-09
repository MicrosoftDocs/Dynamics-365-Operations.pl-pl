---
title: "Tworzenie szablonów rekordów"
description: "Ten artykuł zawiera wprowadzenie do koncepcji szablonów rekordów oraz wyjaśnienia, jak używać tych szablonów do tworzenia rekordów udostępniających informacje."
author: pvillads
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 209e4fb346b8c5a02390996cb1fc8fdbd41ba241
ms.lasthandoff: 03/31/2017


---

# <a name="create-record-templates"></a>Tworzenie szablonów rekordów

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera wprowadzenie do koncepcji szablonów rekordów oraz wyjaśnienia, jak używać tych szablonów do tworzenia rekordów udostępniających informacje.

Szablony rekordów pomagają w szybkim tworzeniu rekordów w programie Microsoft Dynamics 365 for Operations. Istnieje możliwość tworzenia szablonów rekordów tylko dla niektórych typów rekordów w programie Microsoft Dynamics 365 for Operations. Na przykład załóżmy,**** że wprowadzasz dane wynajmu dla wypożyczali samochodów w San Francisco. Ponieważ większość klientów będzie prawdopodobnie pochodziła z San Francisco, byłoby dobrze, gdy pola **Stan**, **Kraju** i **Miasto** na formularzu wynajmu mogły wypełniać się automatycznie **Uwaga:** Szablony mogą być stosowane tylko w odniesieniu do obszarów programu Dynamics 365 for Operations, do których użytkownicy mają dostęp. Jednak wszystkie tytuły szablonów są dla Ciebie widoczne podczas tworzenia nowego rekordu, a także dla innych użytkowników w przypadku tworzenia szablonów, które będą dostępne dla wszystkich użytkowników. Należy to wziąć pod uwagę podczas nadawania nazw szablonom. Na przykład należy unikać nazw zawierających słowo „prowizja”, jeśli poufną informacją jest to, że wynagrodzenia niektórych pracowników mają charakter prowizyjny. Gdy jeden lub więcej szablonów, do których masz dostęp, istnieje dla określonego formularza i próbujesz utworzyć nowy rekord w formularzu, wyświetlany jest strona **Wybierz szablon dla...**. Po wybraniu szablonu z listy jest tworzony nowy rekord, zawierający domyślne informacje utworzone na podstawie wybranego szablonu. Jeśli nie chcesz używać szablonów podczas tworzenia nowych rekordów, zaznacz pole wyboru **Nie pytaj ponownie** na stronie **Wybierz szablon dla**. Aby ponownie wyświetlić okno dialogowe wyboru szablonu, kliknij prawym przyciskiem myszy dowolny rekord, kliknij opcję **Informacje o rekordzie**, a następnie kliknij przycisk **Pokaż zaznaczenie szablonów**.




