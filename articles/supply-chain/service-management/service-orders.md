---
title: Zlecenia serwisowe
description: Zlecenie serwisowe reprezentuje wizytę serwisanta w siedzibie odbiorcy w określonym dniu.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 26a1c693be9581bd26ad43c70a024b0a8115afdf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254246"
---
# <a name="service-orders"></a>Zlecenia serwisowe   

[!include [banner](../includes/banner.md)]


Zlecenie serwisowe reprezentuje wizytę serwisanta w siedzibie odbiorcy w określonym dniu. Każde zlecenie serwisowe składa się z jednego lub większej liczby wierszy zlecenia serwisowego. Wiersze zlecenia serwisowego reprezentują godziny pracy, jaką musi wykonać serwisant, oraz powiązane towary, wydatki i opłaty.

Do wiersza zlecenia serwisowego można dołączać zadania i przedmioty. Umożliwi to następnie grupowanie wierszy zleceń serwisowych według zadań lub przedmiotów. Do wierszy zlecenia serwisowego można również dołączać towary wyświetlane na liście zapasów.

## <a name="create-service-orders"></a>Tworzenie zlecenia serwisowego

Zlecenia serwisowe można tworzyć na podstawie umowy serwisowej i zawartych w niej wierszy. Jednak zlecenia serwisowe skojarzone z umową serwisową można tworzyć tylko w okresie, który jest określony w umowie. Na przykład jeśli umowa serwisowa jest ważna w roku kalendarzowym 2011, można tworzyć zlecenia serwisowe dla tej umowy w dniach od 1 stycznia 2011 r. do 31 grudnia 2011 r.

Można również tworzyć zlecenia serwisowe indywidualnie, bez kojarzenia ich z umową. Takie zlecenia serwisowe mogą służyć do obsługi niezaplanowanych lub jednorazowych wizyt serwisowych. Na przykład w marcu odbiorca prosi o wykonanie dodatkowego serwisu dla dwóch urządzeń, oprócz maszyn określonych w umowie serwisowej. Dla tego zadania tworzysz zlecenia serwisowe, ale nie kojarzysz ich z umową.


> [!NOTE]
> <P>Aby utworzyć zlecenia serwisowe, które nie są powiązane z umową serwisową, należy zaznaczyć pole wyboru <STRONG>Dozwolone bez umowy serwisowej</STRONG> w formularzu <STRONG>Parametry modułu Zarządzanie serwisem</STRONG>.</P>

**Scenariusz**

Poniższy scenariusz opisuje inną sytuację, w której warto utworzyć zlecenie serwisowe, które nie jest powiązane z umową serwisową.

Dyspozytor w firmie odbiera zgłoszenie dotyczące pilnego serwisu windy. Nie czasu na konfigurowanie umowy serwisowej i projektu na wykonanie prac serwisowych. Z tego względu dyspozytor tworzy zlecenie serwisowe bezpośrednio w formularzu **Zlecenia serwisowe**, dołącza zlecenie serwisowe do istniejącego projektu, a następnie tworzy wiersze zlecenia serwisowego. Ponadto dyspozytor tworzy relację zadania lub przedmiotu dla istniejącego zlecenia serwisowego w celu rejestrowania pracy, która nie jest związana z umową serwisową. Aby uzyskać więcej informacji, zobacz [Ręczne tworzenie zleceń serwisowych](create-service-orders-manually.md) i [Tworzenie relacji zadania serwisowego](create-service-task-relations.md).

## <a name="monitor-the-progress-of-service-orders"></a>Monitorowanie postępu realizacji zleceń serwisowych

Aby monitorować postęp realizacji zleceń serwisowych w różnych zespołach i procesach roboczych, można skonfigurować system etapów i kodów przyczyn dla zleceń serwisowych. Dla każdego etapu można określić dozwolone działania. Aby uzyskać więcej informacji, zobacz [Tworzenie kodów przyczyn](create-reason-codes.md).

**Przykład**

Zlecenie serwisowe jest zatwierdzane przez dyspozytora. Dyspozytor aktualizuje etap realizacji zlecenia serwisowego i ustawia kod przyczyny, który wskazuje, że zlecenie serwisowe zostało zwolnione do serwisanta. Serwisant udaje się do siedziby odbiorcy i wykonuje prace serwisowe.

## <a name="specify-item-requirements-for-service-orders"></a>Określanie zapotrzebowań na towary do zleceń serwisowych

Można określić pozycje magazynowe, które są wymagane dla zleceń serwisowych. W tym celu zlecenie serwisowe musi być skojarzone z projektem. Zapotrzebowania na towary dla zlecenia serwisowego są przetwarzane za pomocą projektu. 

**Przykład**

Zlecenia serwisowe utworzone na podstawie umowy serwisowej są przetwarzane przez dyspozytora. Przy pierwszym zleceniu serwisowym dyspozytor zdał sobie sprawę, że serwisantowi potrzebna jest ważna zapasowa część, której nie ma w dostępnych zapasach magazynowych. Tworzy więc zapotrzebowanie na towar dotyczące tej części bezpośrednio ze zlecenia serwisowego.

## <a name="move-and-post-lines"></a>Przenoszenie i księgowanie wierszy

Po powrocie z wizyty serwisowej serwisant modyfikuje i aktualizuje wiersze zlecenia serwisowego. W trakcie tej wizyty serwisowej serwisant wykonał pracę serwisową, która była zaplanowana na następną wizytę. W związku z tym serwisant przenosi wiersze z następnej wizyty serwisowej do bieżącej wizyty serwisowej. Następnie serwisant księguje zlecenie serwisowe. Aby uzyskać więcej informacji, zobacz [Przenoszenie wierszy zlecenia serwisowego](move-service-order-lines.md).

## <a name="cancel-service-orders"></a>Anuluj zlecenia serwisowe

Jedno z pozostałych zleceń serwisowych wygenerowanych dla stycznia stało się nieaktualne z powodu anulowania pracy. W związku z tym dyspozytor anuluje zlecenie serwisowe. Aby uzyskać więcej informacji, zobacz [Anulowanie zleceń serwisowych](cancel-service-orders.md).

## <a name="post-from-projects"></a>Księgowanie z projektów

W końcu każdego tygodnia dyspozytor chce zaksięgować wszystkie zlecenia serwisowe dołączone do określonego projektu. W związku z tym dyspozytor odszukuje odpowiedni projekt w formularzu **Projekty** i księguje zlecenia serwisowe, które zostały ukończone. Aby uzyskać więcej informacji, zobacz [Księgowanie zleceń serwisowych (formularzy klasy)](https://technet.microsoft.com/library/aa574685\(v=ax.60\)).

## <a name="delete-service-orders"></a>Usuń zlecenia serwisowe

W drugiej połowie roku odbiorca doszedł do wniosku, że wizyty serwisowe są zbyt rzadkie. Należy utworzyć nową, liczącą więcej pozycji serię wizyt serwisowych w pozostałym czasie umowy serwisowej. W tym celu należy usunąć istniejące zlecenia serwisowe i utworzyć nowe. Aby uzyskać więcej informacji, zobacz [Usuwanie zleceń serwisowych](delete-service-orders.md).

## <a name="see-also"></a>Informacje dodatkowe

[Zlecenia serwisowe (formularz)](https://technet.microsoft.com/library/aa554361\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]