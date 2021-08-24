---
title: Limit progowy i limit progowy wyjątków
description: W tym temacie opisano progi i limity wyjątków dotyczące potrącanych podatków w źródle (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 510a8904cc36821dbb22d2affab5aa32c269e6d8c57144cc1f4ef3e1ac448334
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774262"
---
# <a name="threshold-limit-and-exception-threshold-limit"></a>Limit progowy i limit progowy wyjątków

[!include [banner](../includes/banner.md)]

W tym temacie opisano progi i limity wyjątków dotyczące potrącanych podatków w źródle (TDS). IdentyfikatorY TDS faktur i płatności są zawsze obliczane z uwzględnieniem limitu progowego i limitu progu wyjątku zdefiniowanego dla składników podatku TDS na stronie **Składniki potrąconej zaliczki na podatek**. Składniki podatku TDS są dołączane do kodów podatku TDS, które są zawarte w grupach podatków TDS. Grupy podatków TDS są dołączane do dostawców i odbiorców w celu obliczania TDS na poziomie faktury lub na poziomie płatności.

Identyfikator TDS jest obliczany, jeśli kwota transakcji lub skumulowanych transakcji zaksięgowanych z określoną grupą TDS dla dostawcy przekracza limit progowy określony na stronie **Składniki potrąconej zaliczki na podatek**. Identyfikator TDS zostanie obliczony dopiero po przekroczeniu określonego limitu progowego skumulowanej kwoty transakcji.

Jeśli wraz z limitem progowym dla składnika TDS zostanie określony limit progowy wyjątku, identyfikator TDS jest obliczany, gdy określona kwota transakcji przekracza limit progu wyjątku, nawet jeśli skumulowana kwota transakcji nie przekracza określonego limitu progowego.

### <a name="example"></a>Przykład
Składnik podatku o nazwie TDS jest ustawiany i dołączany do grupy podatków TDS o nazwie Zleceniobiorcy. Próg został zdefiniowany jako 50 000, a próg wyjątku został zdefiniowany jako 20 000 dla składnika podatku TDS. Zleceniobiorcy grupy TDS są definiowani jako domyślna grupa TDS dla dostawcy 1.

Faktura zakupu 001 jest księgowana dla dostawcy 1 na 10000. Identyfikator TDS nie jest obliczany dla faktury, ponieważ kwota faktury nie przekroczyła limitu progowego lub limitu progowego wyjątku. Faktura zakupu 002 jest księgowana dla dostawcy 1 na 25,000. TDS jest obliczany dla faktury, ponieważ kwota faktury przekroczyła próg wyjątku. Faktura zakupu 003 jest księgowana dla Dostawcy 1 na 20 000. Identyfikator TDS jest obliczany dla faktury, ponieważ łączna kwota faktury z trzech faktur wystawionych dla dostawcy przekroczyła limit progowy. Identyfikator TDS jest obliczany na wszystkich fakturach wystawionych dla dostawcy, dla którego nie został on wcześniej obliczony. Dlatego też identyfikator TDS jest obliczany na kwotę 30 000, czyli łączną kwotę faktury dla faktur 001 i 003.

Limit progowy i limit progowy wyjątku nie są uwzględniane przy obliczaniu TDS, jeśli pole wyboru **Próg przekroczenia progu** jest zaznaczone dla kodów podatku TDS w grupie TDS, która jest dołączona do transakcji. Limit progowy nie będzie używany w kodach podatków TDS w grupie TDS, dla której jest używane pole wyboru **Przeoczenie progu**.

Jeśli dla niektórych faktur jest zaznaczone pole wyboru **Przeoczenie progu**, ale nie zostało zaznaczone dla innych faktur utworzonych dla określonego dostawcy/odbiorcy, obliczenie TDS bez przeoczenia limitu progowego dla kilku faktur może mieć miejsce z uwzględnieniem kwoty skumulowanej na wszystkich fakturach, dla których nie obliczono wcześniej identyfikatorów TDS.

Na przykład limit progu wynosi 25000. Następujące faktury są tworzone dla dostawcy A.

- Faktura 1 – 20000 — (Pole wyboru **Przeoczenie progu nie jest zaznaczone**). Identyfikator TDS nie jest obliczany.

- Faktura 2 – 4000 — (Pole wyboru **Przeoczenie progu nie jest zaznaczone**). TDS jest obliczany na podstawie 4000.

- Faktura 2 – 3000 — (Przeocz pole wyboru **Przeocz wartość progową** nie jest zaznaczone). Identyfikator TDS jest obliczany jako suma kwoty faktury, 27,000 (20000+4000+3000) przekracza limit progowy. Identyfikator TDS jest obliczany na podstawie skumulowanej kwoty faktur, dla których identyfikator TDS nie został wcześniej obliczony, 23 000 (20000+3000).
