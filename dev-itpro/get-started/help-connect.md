---
title: "Łączenie z systemem Pomocy"
description: "W tym temacie opisano składniki systemu Pomocy w programie Microsoft Dynamics 365 for Finance and Operations, sposoby ich podłączania oraz podstawowe zasady tworzenia pomocy niestandardowej."
author: margoc
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 425e87f8b667b53fcc950730dc4ece6330503d66
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017


---

# <a name="connect-the-help-system"></a>Łączenie z systemem Pomocy

[!include[banner](../includes/banner.md)]


W tym temacie opisano składniki systemu Pomocy w programie Microsoft Dynamics 365 for Finance and Operations. Omówiono sposoby podłączania tych składników oraz podstawowe zasady tworzenia pomocy niestandardowej. 

## <a name="help-architecture"></a>Architektura modułu Pomoc
Poniższa ilustracja pokazuje części systemu Pomocy w programie Dynamics 365 for Finance and Operations. Wewnętrzny system Pomocy ściąga artykuły z witryny programu Dynamics 365 for Finance and Operations pod adresem https://docs.microsoft.com oraz przewodniki po zadaniach przechowywane w narzędziu do modelowania procesów biznesowych w usłudze Lifecycle Services (LCS). 
> [!NOTE]
> Funkcje oznaczone w diagramie gwiazdką (\*) są planowane, ale jeszcze niedostępne. [![Architektura modułu Pomoc](./media/help-architecture.png)](./media/help-architecture.png)


## <a name="connecting-the-help-system"></a>Łączenie z systemem Pomocy
> [!NOTE]
> Karta **Przewodniki po zadaniach** jest obecnie niedostępna w programach Microsoft Dynamics 365 for Talent i Microsoft Dynamics 365 for Retail. Obecnie pracujemy nad włączeniem tej funkcjonalności w przyszłym wydaniu. Przewodniki po zadaniach w sekcji Rozpoczęcie pracy w module Talent pozostają dostępne i oferują podstawowe funkcje. Ponadto jest dostępna pomoc dla procedur w witrynie docs.microsoft.com ([docs.microsoft.com/dynamics365/operations](/dynamics365/#pivot=solutions&panel=solutions_operations)) dla aplikacji Retail i Talent.
 

Za pomocą strony **Parametry systemowe** administratorzy łączą elementy systemu Pomocy i je implementują. [![Formularz Parametry systemowe z ustawieniami Pomocy](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Na stronie **Parametry systemowe** wykonaj następujące czynności:

> [!IMPORTANT]
> Podczas pierwszego otwierania karty **Pomoc** należy utworzyć połączenie z usługą Lifecycle Services. Kliknij łącze na środku formularza, poczekaj na nawiązanie połączenia, zamknij okno dialogowe i kliknij przycisk **OK**, co spowoduje przejście do strony **Parametry systemu**.[![Łączenie z usługą LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)

1.  Wybierz projekt Lifecycle Services, z którym chcesz się połączyć.
2.  Wybierz biblioteki BPM (w ramach wybranego projektu), z których będą pobierane nagrania zadań.
    - Pakiety zawartości Microsoft dla programu Finance and Operations znajdują się w ujednoliconej bibliotece QPC z lutego 2017 r. dla programu Microsoft Dynamics 365 for Finance and Operations. 
    - Dla programu Retail opublikujemy bibliotekę w lipcu. 
    - Nie trzeba wybierać biblioteki dla programu Talent — połączenie z właściwą biblioteką jest tworzone automatycznie. 

3.  Ustaw kolejność wyświetlania bibliotek BPM. Określa kolejność wyświetlania nagrań z bibliotek w okienku **pomocy**.

Po wykonaniu tych kroków można otworzyć okienko **pomocy** i kliknąć kartę **Przewodniki po zadaniach**. Teraz widać przewodniki po zadaniach, które mają zastosowanie do strony aktualnie wyświetlanej w programie Finance and Operations. Jeśli nie zostaną znalezione żadne przewodniki po zadaniach, możesz wprowadzić słowa kluczowe, aby doprecyzować wyszukiwanie.

### <a name="showing-translated-task-guides"></a>Wyświetlanie przetłumaczonych przewodników po zadaniach

Przetłumaczone przewodniki po zadaniach po raz pierwszy umieszczono w ujednoliconej bibliotece APQC w wydaniu z maja 2016 r. oraz w bibliotece ułatwiającej rozpoczęcie pracy. Aby wyświetlić przetłumaczone przewodniki po zadaniach w pomocy w programie Finance and Operations, upewnij się, że masz połączenie z biblioteką z maja. Język wyświetlania przetłumaczonego przewodnika po zadaniu jest kontrolowany przez każdego użytkownika w ustawieniach języka w oknie **Opcje** &gt; **Preferencje**. 

> [!NOTE]
> Mimo że przetłumaczono wiele przewodników po zadaniach, obecnie klient programu Finance and Operations nie pokazuje nazw przetłumaczonych przewodników. Ponadto w majowej bibliotece są dostępne tłumaczenia tylko przewodników po zadaniach opublikowanych w lutym 2016 r. Opublikujemy zaktualizowaną bibliotekę z dodatkowymi tłumaczeniami.
> -   Jeśli przewodnik po zadaniu został przetłumaczony, po otwarciu przewodnika jego cały tekst będzie wyświetlany w wybranym języku.
> -   Jeśli przewodnik po zadaniu nie został jeszcze przetłumaczony, po otwarciu przewodnika tylko część tekstu (formanty) będzie wyświetlana w wybranym języku.

## <a name="creating-custom-help"></a>Tworzenie pomocy niestandardowej
W programie Finance and Operations i aplikacji Retail można utworzyć pomoc niestandardową poprzez utworzenie nagrań zadań odpowiadających konkretnemu wdrożeniu i zapisanie ich w bibliotece procesów biznesowych LCS. Nie można tworzyć niestandardowych przewodników po zadaniach dla modułu Talent. 

W przypadku partnerów: jeśli zostanie podniesiony poziom biblioteki do firmowej i zostanie ona uwzględniona w rozwiązaniu, będzie dostępna dla klientów. Można również utworzyć kopię ujednoliconej globalnej biblioteki APQC, a następnie otworzyć tę kopię, otwierać z niej nagrania zadań, modyfikować je i zapisywać nagrania z wprowadzonymi zmianami. Aby uzyskać więcej informacji, zobacz [Jak utworzyć nagrania zadań do użycia w dokumentacji lub na szkoleniach](../user-interface/task-recorder.md).

<a name="see-also"></a>Informacje dodatkowe
--------

[Omówienie Pomocy](help-overview.md)

[Omówienie rejestratora zadań](../user-interface/task-recorder.md)

[Jak utworzyć nagrania zadań do użycia w dokumentacji lub na szkoleniach](../user-interface/task-recorder-training-docs.md)





