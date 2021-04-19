---
title: Tworzenie zapotrzebowań na towary na podstawie zleceń serwisowych
description: Jeśli konieczne jest zarezerwowanie określonych towarów dla zlecenia serwisowego, można utworzyć zapotrzebowanie na pozycje magazynowe dla takiego zlecenia.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 650d02d2160757d9629e4deb1e9217c85e9d01df
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831633"
---
# <a name="create-item-requirements-for-service-orders"></a>Tworzenie zapotrzebowań na towary na podstawie zleceń serwisowych 

[!include [banner](../includes/banner.md)]


Można utworzyć zlecenie serwisowe do śledzenia i zarządzania usługami świadczonymi odbiorcom. Jeśli konieczne jest zarezerwowanie określonych towarów dla zlecenia serwisowego, można utworzyć zapotrzebowanie na pozycje magazynowe dla takiego zlecenia. Zapotrzebowania na towary mogą być realizowane bezpośrednio z magazynu lub mogą zainicjować zlecenie produkcyjne dla towaru.

Dzięki użyciu zapotrzebowań na towary zamiast transakcji towarowych można zaplanować czas dostawy dokładnie w momencie użycia towaru oraz można utworzyć zamówienie zakupu, dołączyć towar do struktury umowy handlowej i dołączyć zapotrzebowanie na towary w planie produkcyjnym.

Zapotrzebowania na towary dla zlecenia serwisowego są przetwarzane za pomocą projektu. W celu utworzenia zapotrzebowania na towary dla zlecenia serwisowego, takie zlecenie musi być powiązane z projektem. Po utworzeniu zapotrzebowania na towary dla zlecenia serwisowego można wyświetlić to zapotrzebowanie w formularzu **Projekty** dla wybranego projektu.

## <a name="create-an-item-requirement-for-a-service-order"></a>Tworzenie zapotrzebowania na towary dla zlecenia serwisowego

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.

2.  Wybierz zlecenie serwisowe, dla którego chcesz utworzyć zapotrzebowanie na towar.

3.  W **okienku akcji** na karcie **Wysyłka** kliknij opcję **Zapotrzebowanie na towary**.

4.  W formularzu **Zapotrzebowanie na towary** wprowadź informacje dla wymaganego towaru. Aby uzyskać więcej informacji o konkretnych polach, zobacz [Zapotrzebowanie na towary (formularz)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).

## <a name="create-an-item-requirement-for-a-service-agreement"></a>Tworzenie zapotrzebowania na towary do umowy serwisowej

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.

2.  Otwórz umowę serwisową, dla której chcesz utworzyć zapotrzebowanie na towar.

3.  Na skróconej karcie **Wiersze** kliknij przycisk **Dodaj**, aby utworzyć nowy wiersz.

4.  W polu **Typ transakcji** wybierz opcję **Towar**.

5.  W polu **Ustawienia pozycji** wybierz opcję **Zapotrzebowanie na towary**.

6.  W polu **Numer pozycji** wybierz towar, który jest wymagany dla umowy serwisowej.

7.  Na skróconej karcie **Szczegóły wiersza** na karcie **Wymiary produktu** w polu **Oddział** wybierz oddział zapasów dla towaru.

8.  Aby utworzyć zlecenie serwisowe z wiersza umowy, na skróconej karcie **Wiersze** kliknij opcję **Utwórz zlecenia serwisowe**, a następnie wprowadź odpowiednie informacje w formularzu **Utwórz zlecenia serwisowe**. 


## <a name="see-also"></a>Informacje dodatkowe

[Automatyczne tworzenie zleceń serwisowych](create-service-orders-automatically.md).

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]