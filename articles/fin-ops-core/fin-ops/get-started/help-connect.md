---
title: Łączenie z systemem Pomocy
description: W tym temacie opisano składniki systemu Pomocy dla aplikacji Finance and Operations i sposoby ich łączenia oraz podstawowe zasady tworzenia pomocy niestandardowej.
author: margoc
manager: AnnBe
ms.date: 10/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 491024c9c3d6c7d20ef212e167ceab6abac8dac7
ms.sourcegitcommit: d554faca895609b8124bf2ea5aca5a55c407534a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "2537862"
---
# <a name="connect-the-help-system"></a>Łączenie z systemem Pomocy

[!include [banner](../includes/banner.md)]

W tym temacie opisano składniki systemu pomocy dla Finance and Operations, takie jak Dynamics 365 Finance, Supply Chain Management, Retail i Talent. Omówiono sposoby podłączania tych składników oraz podstawowe zasady tworzenia pomocy niestandardowej.

## <a name="help-architecture"></a>Architektura modułu Pomoc

Poniższa ilustracja pokazuje części Pomocy systemu. Wewnętrzny system Pomocy ściąga artykuły z witryny pod adresem https://docs.microsoft.com oraz przewodniki po zadaniach przechowywane w narzędziu do modelowania procesów biznesowych w usłudze Lifecycle Services (LCS).

> [!NOTE]
> Funkcje oznaczone w diagramie gwiazdką (\*) są planowane, ale jeszcze niedostępne.

[![Architektura modułu Pomoc](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Łączenie z systemem Pomocy

> [!NOTE]
> Karta **Przewodniki po zadaniach** jest obecnie niedostępna w programach Microsoft Dynamics 365 Talent lub Retail. Obecnie pracujemy nad włączeniem tej funkcjonalności w przyszłym wydaniu. Przewodniki po zadaniach w sekcji Rozpoczęcie pracy w module Talent pozostają dostępne i oferują podstawowe funkcje. Pomoc dotycząca procedur jest również dostępna w witrynie docs.microsoft.com w odniesieniu do Retail i Talent.

Za pomocą strony **Parametry systemowe** administratorzy łączą elementy systemu Pomocy i je implementują.

[![Formularz Parametry systemu z ustawieniami Pomocy](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

Na stronie **Parametry systemu** wykonaj następujące kroki:

> [!IMPORTANT]
> Podczas pierwszego otwierania karty **Pomoc** należy utworzyć połączenie z usługą Lifecycle Services. Kliknij łącze na środku formularza, poczekaj na nawiązanie połączenia, zamknij okno dialogowe i kliknij przycisk **OK**, co spowoduje przejście do formularza **Parametry systemu**.
>
> [![Podłączanie do LCS](./media/connect-to-lcs-crop-1024x365.png "Podłączanie do LCS")](./media/connect-to-lcs-crop.png)

1. Wybierz projekt Lifecycle Services, z którym chcesz się połączyć.
2. Wybierz biblioteki BPM (w ramach wybranego projektu), z których będą pobierane nagrania zadań.
3. Ustaw kolejność wyświetlania bibliotek BPM. Określa kolejność wyświetlania nagrań z bibliotek w okienku **pomocy**.

Po wykonaniu tych kroków można utworzyć okienko **Pomoc** i kliknąć kartę **Przewodniki zadań**. Zobaczysz przewodniki zadań mające zastosowanie do strony aktualnie wyświetlonej w aplikacjach Finance and Operations. Jeśli nie zostaną znalezione żadne przewodniki po zadaniach, możesz wprowadzić słowa kluczowe, aby doprecyzować wyszukiwanie.

### <a name="showing-translated-task-guides"></a>Wyświetlanie przetłumaczonych przewodników po zadaniach

Przetłumaczone przewodniki po zadaniach po raz pierwszy umieszczono w ujednoliconej bibliotece APQC w wydaniu z maja 2016 r. oraz w bibliotece ułatwiającej rozpoczęcie pracy. Aby wyświetlić przetłumaczone przewodniki po zadaniach w pomocy w aplikacjach Finance and Operations, upewnij się, że masz połączenie z biblioteką z maja. Język wyświetlania przetłumaczonego przewodnika po zadaniu jest kontrolowany przez każdego użytkownika w ustawieniach języka w oknie **Opcje** &gt; **Preferencje**.

> [!NOTE]
> Mimo że przetłumaczono wiele przewodników po zadaniach, obecnie klient nie pokazuje nazw przetłumaczonych przewodników. Ponadto w majowej bibliotece są dostępne tłumaczenia tylko przewodników po zadaniach opublikowanych w lutym 2016 r. Opublikujemy zaktualizowaną bibliotekę z dodatkowymi tłumaczeniami.
>
> - Jeśli przewodnik po zadaniu został przetłumaczony, po otwarciu przewodnika jego cały tekst będzie wyświetlany w wybranym języku.
> - Jeśli przewodnik po zadaniu nie został jeszcze przetłumaczony, po otwarciu przewodnika tylko część tekstu (formanty) będzie wyświetlana w wybranym języku.

## <a name="creating-custom-help"></a>Tworzenie pomocy niestandardowej

Można przewodników po zadaniach do tworzenia pomocy niestandardowej lub połączenia witryny sieci Web z okienkiem pomocy.

### <a name="create-custom-help-with-task-guides"></a>Tworzenie Pomocy niestandardowej przy użyciu przewodników po zadaniach

W Finance, Supply Chain Management i aplikacji Retail można utworzyć pomoc niestandardową poprzez utworzenie nagrań zadań odpowiadających konkretnemu wdrożeniu i zapisanie ich w bibliotece procesów biznesowych LCS. Nie można tworzyć niestandardowych przewodników po zadaniach dla modułu Talent.

W przypadku partnerów: jeśli zostanie podniesiony poziom biblioteki do firmowej i zostanie ona uwzględniona w rozwiązaniu, będzie dostępna dla klientów. Można również utworzyć kopię ujednoliconej globalnej biblioteki APQC, a następnie otworzyć tę kopię, otwierać z niej nagrania zadań, modyfikować je i zapisywać nagrania z wprowadzonymi zmianami. Aby uzyskać więcej informacji, zobacz [Jak utworzyć nagrania zadań do użycia w dokumentacji lub na szkoleniach](../../dev-itpro/user-interface/task-recorder.md).

### <a name="connect-a-custom-site"></a>Łączenie z niestandardową witryną

Firma Microsoft oferuje wytyczne i przykładowy kod opisujące tworzenie oraz łączenie witryny Pomocy niestandardowej do okienka Pomocy. Aby uzyskać więcej informacji, zobacz:

- [Tworzenie pomocy niestandardowej dla aplikacji Finance and Operations (oficjalny dokument)](https://go.microsoft.com/fwlink/?linkid=2041185)
- [Repozytorium GitHub Pomocy niestandardowej](https://github.com/microsoft/dynamics356f-o-custom-help)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie Pomocy](help-overview.md)

[Omówienie rejestratora zadań](../../dev-itpro/user-interface/task-recorder.md)

[Jak utworzyć nagrania zadań do użycia w dokumentacji lub na szkoleniach](../../dev-itpro/user-interface/task-recorder-training-docs.md)
