---
title: Konfigurowanie i przetwarzanie płatności pomostowych
description: W tym artykule wyjaśniono, jak skonfigurować i przetwarzać pomostowe płatności klientów. Płatność pomostowa to płatność księgowana w księdze głównej w dwóch krokach.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, VendPaymMode, LedgerJournalTable, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, LedgerJournalTransDaily
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f0609e333fb16ba189b6a971f88fbb5bf900fec
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887985"
---
# <a name="set-up-and-process-bridged-payments"></a>Konfiguruj i przetwarzaj płatności pomostowe

[!include [banner](../includes/banner.md)]

Płatność pomostowa to płatność księgowana w księdze głównej w dwóch krokach. Zwykle takie podejście jest stosowane, gdy jako metoda płatności jest ustawiona Metoda płatności **Bank** i transakcje należy księgować na koncie bankowym tylko wtedy, gdy wyczyszczy bank. Można go jednak użyć także dla konta księgowego. W takim przypadku podczas przetwarzania księgowania pomostowego kwota zostanie przesunana z jednego konta głównego na inne konto główne.

Płatności pomostowe można tworzyć z rozrachunków z dostawcami lub rozrachunków z odbiorcami. W tym artykule opisano sposób konfigurowania księgowania pomostowego dla rozrachunków z odbiorcami, ale kroki dotyczące transakcji rozrachunków z dostawcami są podobne.

## <a name="set-up-bridging-posting"></a>Konfigurowanie księgowania mostkowania

Aby korzystać z księgowania pomostowego, należy skonfigurować jedną lub więcej metod płatności, aby były one używać metody **księgowania pomostowego**. Następnie należy wybrać konto pomostowe.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami &gt; Ustawienia płatności &gt; Metody płatności**.
2. Umożliwia wybranie istniejącej metody płatności, aby umożliwić dla nich księgowanie pomostowe. Można również utworzyć nową metodę płatności.
3. Zaznacz pole wyboru **Księgowanie pomostowe**.
4. W polu **Konto pomostowe** wybierz konto główne, na które powinny być księgowane płatności przed ich wyczyszczeniem na koncie bankowym.
5. Zamknij stronę.

## <a name="process-and-transfer-bridging-posting"></a>Przetwarzanie i przenoszenie księgowania pomostowego

Aby utworzyć i przetworzyć księgowanie pomostowe, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami &gt; Płatności &gt; Arkusz płatności klienta**.
2. Wybierz **Nowa**, aby utworzyć arkusz.
3. W polu **Nazwa** wprowadź nazwę.
4. Dodaj wiersze do arkusza płatności odbiorcy i wybierz metodę płatności skonfigurowaną dla księgowania pomostowego.
5. Księguj arkusz. Transakcje zostaną zaksięgowane na koncie głównym wybranym w polu **Konto pomostowe** w poprzedniej procedurze.

Gdy transakcje wyczyszczysz bank i chcesz przenieść płatność z konta pomostowego na konto płatności określone dla metody płatności, wykonaj następujące kroki.

1. Przejdź do pozycji **Księga główna &gt; Wpisy w arkuszu &gt; Arkusze finansowe**.
2. Wybierz **Nowa**, aby utworzyć arkusz.
3. W polu **Nazwa** wprowadź nazwę.
4. Wybierz **opcję Wiersze**, aby otworzyć szczegóły arkusza.
5. Należy kliknąć kolejno **Funkcje &gt; Wybierz transakcje pomostowe**.
6. Zaznacz każdą wyczyszkną płatność, a następnie wybierz **akceptację**.
7. Księguj arkusz.
