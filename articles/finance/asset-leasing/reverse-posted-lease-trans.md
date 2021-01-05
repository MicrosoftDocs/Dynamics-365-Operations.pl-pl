---
title: Wycofywanie zaksięgowanych transakcji wynajmu
description: W tym temacie wyjaśniono, jak wycofać zaksięgowaną transakcję wynajmu. Każdą transakcję utworzoną za pośrednictwem modułu Wynajem składnika majątku można wycofać.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 259fd8f41eade1e873225f0d95c499c8cb8c1a6a
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "4446999"
---
# <a name="reverse-posted-lease-transactions"></a>Wycofywanie zaksięgowanych transakcji wynajmu

[!include [banner](../includes/banner.md)]

Każdą transakcję utworzoną za pośrednictwem modułu Wynajem składnika majątku można wycofać. Transakcje wycofane za pośrednictwem modułu Wynajem składnika majątku powodują aktualizację danych wynajmu. W związku z tym aktualizują także wartości bilansowe zobowiązania z tytułu wynajmu i składnika majątku z prawem do użytkowania (PDU).

Aby utworzyć transakcję stornującą dla dzierżawy, należy wykonać następujące kroki.

1. Na stronie **Transakcje składnika majątku** lub **Transakcje zobowiązań** wybierz transakcję, a następnie wybierz pozycję **Wycofaj transakcję**.
2. W wyświetlonym oknie dialogowym można edytować datę, z którą ma zostać zaksięgowany wpis stornujący. Domyślnie w polu **Data** jest ustawiana data księgowania wybranej transakcji. Wpis stornujący nie może zostać zaksięgowany wcześniej niż w pierwotnym dniu księgowania wybranej transakcji.
3. Kliknij przycisk **OK**. Jest księgowany wpis w arkuszu, który powoduje wycofanie wybranego wpisu. Wycofanie jest wyświetlane na stronie **Transakcje składnika majątku** lub **Transakcje zobowiązań**, a suma netto bieżącego salda wyświetlana na stronie jest aktualizowana.

Po wybraniu opcji **Śledzenie wycofania** zostanie wyświetlone okno dialogowe, w którym są wyświetlane zarówno oryginalne transakcje, jak i transakcje wycofane, wraz z połączoną liczbą nazywaną *numerem śledzenia*. Aby wycofania były bardziej zrozumiałe i przejrzyste, można je również śledzić, korzystając z harmonogramów wynajmu.

W polu **Najnowszy numer arkusza** na stronie **Harmonogram** są wyświetlane numery arkuszy transakcji. Po wycofaniu transakcji to pole jest aktualizowane numerem arkusza transakcji stornującej. Ponadto jest zaznaczane pole wyboru **Wycofane**, aby wskazać, że transakcja została wycofana, oraz jest zaznaczane pole **Zaksięgowano**.

## <a name="revoke-a-reversed-transaction"></a>Anulowanie wycofanej transakcji

Aby anulować wycofaną transakcję, należy wykonać następujące kroki.

1. Na stronie **Harmonogram** lub **Transakcje** wybierz oryginalną transakcję.
2. Wykonaj jeden z następujących kroków:

    - Jeśli wybrano transakcję na stronie **Harmonogram**, należy wykonać kroki tworzenia arkusza podane w temacie [Tworzenie miesięcznych wpisów w arkuszu w partii](create-monthly-journals-batch.md). Należy ręcznie zaksięgować arkusz.
    - Jeśli wybrano transakcję na stronie **Transakcje**, należy wybrać opcję **Wycofaj transakcję**. Zostanie wyświetlony komunikat z informacją, że anulowanie jest anulowaniem wcześniejszego wycofania i można edytować datę księgowania tego anulowania. Jednak daty, które można wprowadzić w polu **Data**, zależą od ogólnych weryfikacji biznesowych dokonywanych w organizacji. 

3. Kliknij przycisk **OK**. Jest księgowany wpis w arkuszu, który powoduje wycofanie wybranego wpisu. Wycofanie jest wyświetlane na stronie **Transakcje**, a suma netto bieżącego salda jest przywracana do wartości sprzed pierwszego wycofania. W związku z tym wpływ wycofania na salda jest niwelowany.

Po wybraniu opcji **Śledzenie wycofania** zostanie wyświetlone okno dialogowe, w którym są wyświetlane zarówno oryginalne transakcje, jak i transakcje wycofane, wraz z połączonym numerem śledzenia.

Odwołania można również śledzić na odpowiedniej stronie **Harmonogramy**. Pole **Wycofaj** jest czyszczone, podczas gdy pole **Arkusz zaksięgowany** jest zaznaczane. Ponadto pole **Najnowszy numer arkusza** jest aktualizowana o numer arkusza transakcji anulowania, a pole **Numer arkusza** jest aktualizowane numerem arkusza wycofywania.
