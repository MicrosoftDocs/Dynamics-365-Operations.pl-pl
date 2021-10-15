---
title: Konfigurowanie środowiska pomocy dla aplikacji Finance and Operations
description: Ten temat zawiera informacje dotyczące składników systemu pomocy dla niektórych aplikacji Microsoft Dynamics 365.
author: margoc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3a6c37822e84ba08fa0720ed2b3912cbec1448e3
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2021
ms.locfileid: "7594864"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a>Konfigurowanie środowiska pomocy dla aplikacji Finance and Operations

[!include [banner](../includes/banner.md)]

W tym temacie znajduje się omówienie składników systemu pomocy dla aplikacji Finance and Operations, takich jak Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce i Dynamics 365 Human Resources. W tym temacie omówiono również sposób łączenia tych składników oraz przedstawiono podsumowanie procesu tworzenia pomocy niestandardowej.

## <a name="help-architecture"></a>Architektura modułu Pomoc

Aplikacje Finance and Operations oferują omówienia koncepcyjne i inne tematy opublikowane w witrynie [dokumentacja Microsoft Dynamics 365](/dynamics365/). Następnie można uzyskać dostęp do tej zawartości za pomocą okienka **Pomoc** w danym produkcie. Poniższa ilustracja pokazuje części Pomocy systemu.

[![Architektura modułu Pomoc.](./media/help-architecture.png)](./media/help-architecture.png)

System pomocy w danym produkcie pobiera artykuły z witryny docs.microsoft.com i innych połączonych witryn internetowych. Pobierane są również przewodniki zadań przechowywane w Narzędziu do modelowania procesów biznesowych (BPM) w usługach Microsoft Dynamics Lifecycle Services (LCS).

## <a name="adding-task-guides"></a>Dodawanie przewodników zadań

> [!NOTE]
> Karta **Przewodniki zadań** nie jest obecnie dostępna w aplikacjach Human Resources i Commerce. <!--We are currently working to enable this functionality in a future release.--> Natomiast przewodniki po zadaniach w sekcji Rozpoczęcie pracy w module Human Resources pozostają dostępne i oferują podstawowe funkcje. Pomoc dotycząca procedur aplikacji Human Resources oraz Commerce jest dostępna w witrynie [dokumentacja Microsoft Dynamics 365](/dynamics365/).

Na stronie **Parametry systemowe** administratorzy systemu mogą konfigurować dostęp do odpowiednich bibliotek przewodników zadań na potrzeby implementacji.

> [!NOTE]
> - Aby skonfigurować pomoc, musisz się zalogować przy użyciu konta w tej samej dzierżawie, w której jest wdrożona aplikacja.
> - Nie można połączyć się z biblioteką LCS z wystąpienia aplikacji działającej na lokalnym wirtualnym dysku twardym (VHD).

[![Formularz Parametry systemu z ustawieniami Pomocy.](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

Aby skonfigurować przewodniki zadań dla rozwiązania, wykonaj poniższe kroki na stronie **Parametry systemowe**.

> [!IMPORTANT]
> Podczas pierwszego otwierania karty **Pomoc** należy utworzyć połączenie z usługą Lifecycle Services. Wybierz link w środku formularza, poczekaj na nawiązanie połączenia, zamknij okno dialogowe i wybierz przycisk **OK**, co spowoduje przejście do formularza **Parametry systemowe**.
>
> [![Nawiązywanie połączenia z usługą LCS](./media/connect-to-lcs-crop-1024x365.png "Nawiązywanie połączenia z usługą LCS.")](./media/connect-to-lcs-crop.png)

1. Wybierz projekt Lifecycle Services, z którym chcesz się połączyć.
2. Wybierz biblioteki BPM (w ramach wybranego projektu), z których będą pobierane nagrania zadań.
3. Ustaw kolejność wyświetlania bibliotek BPM. Kolejność wyświetlania to porządek, w jakim nagrania zadań z bibliotek będą pojawiać się w okienku **Pomoc**.

Po wykonaniu tych kroków można utworzyć okienko **Pomoc** i wybrać kartę **Przewodniki zadań**. Zobaczysz przewodniki zadań mające zastosowanie do strony aktualnie wyświetlonej w aplikacjach Finance and Operations. Jeśli nie zostaną znalezione żadne przewodniki po zadaniach, możesz wprowadzić słowa kluczowe, aby doprecyzować wyszukiwanie.

### <a name="showing-translated-task-guides"></a>Wyświetlanie przetłumaczonych przewodników po zadaniach

Przetłumaczone przewodniki po zadaniach po raz pierwszy opublikowano w ujednoliconej bibliotece APQC w wydaniu z maja 2016 r. oraz w bibliotece ułatwiającej rozpoczęcie pracy. Aby wyświetlić pomoc przetłumaczonego przewodnika zadania, upewnij się, że rozwiązanie Dynamics 365 zostało połączone z biblioteką z maja 2016 r. Użytkownicy mogą zmienić język wyświetlonego przewodnika zadania, zmieniając ustawienia języka w obszarze **Opcje** &gt; **Preferencje**.

> [!NOTE]
> Mimo że przetłumaczono wiele przewodników zadań, klient obecnie nie pokazuje nazw przetłumaczonych przewodników zadań. Dodatkowo w bibliotece z maja 2016 r. są dostępne tylko tłumaczenia przewodników zadań opublikowanych w lutym 2016 r. Microsoft opublikuje zaktualizowaną bibliotekę zawierającą dodatkowe tłumaczenia.
>
> - Jeśli przewodnik po zadaniu został przetłumaczony, po otwarciu przewodnika jego cały tekst będzie wyświetlany w wybranym języku.
> - Jeśli przewodnik po zadaniu nie został jeszcze przetłumaczony, po otwarciu przewodnika tylko część tekstu (formanty) będzie wyświetlana w wybranym języku.

## <a name="adding-custom-help"></a>Dodawanie pomocy niestandardowej

Przewodników zadań można używać do tworzenia pomocy niestandardowej. Można również połączyć witrynę internetową z okienkiem **Pomoc**.

### <a name="create-custom-help-by-using-task-guides"></a>Tworzenie przewodników zadań pomocy niestandardowej

Pomoc niestandardową dla obsługiwanych aplikacji można utworzyć, tworząc nagrania zadań odpowiadające implementacji i zapisując je w bibliotece procesów biznesowych w usługach LCS. Nie można tworzyć niestandardowych przewodników po zadaniach dla aplikacji Human Resources.

Jeśli jesteś partnerem i podwyższasz status biblioteki do biblioteki firmowej oraz dołączasz ją do rozwiązania, będzie ona dostępna dla Twoich klientów. Można również utworzyć kopię ujednoliconej biblioteki APQC, a następnie otworzyć nagrania zadań w kopii, edytować je i zapisywać zmiany. Więcej informacji można znaleźć w see [Zasoby Rejestratora zadań](../../dev-itpro/user-interface/task-recorder.md).

### <a name="connect-a-custom-help-site"></a>Łączenie z niestandardową witryną pomocy

Aplikacje Finance and Operations są rzadko używane w gotowej postaci. Zamiast tego rozwiązanie jest dostosowywane i rozszerzane w celu dopasowania do potrzeb organizacji. Można również dostosowywać i rozszerzać środowisko pomocy. Można na przykład dodać niestandardową pomoc do okienka **Pomoc** w produkcie.

Firma Microsoft udostępniła zestaw narzędzi ułatwiających wdrażanie i łączenie pomocy niestandardowej z okienkiem **Pomoc**. Aby uzyskać informacje o tym, jak można skonfigurować niestandardowe rozwiązanie pomocy połączone z okienkiem **Pomoc**, zapoznaj się z [omówieniem pomocy niestandardowej](../../dev-itpro/help/custom-help-overview.md).

Aby współpracować z firmą Microsoft w zakresie tworzenia do narzędzi i procesów ułatwiających dostosowywanie pomocy, wypełnij formularz pod adresem [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).

## <a name="see-also"></a>Informacje dodatkowe

[System Pomocy](help-overview.md)  
[Omówienie pomocy niestandardowej](../../dev-itpro/help/custom-help-overview.md)  
[Zasoby rejestratora zadań](../../dev-itpro/user-interface/task-recorder.md)  
[Tworzenie dokumentacji lub szkolenia za pomocą Rejestratora zadań](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[Repozytorium GitHub pomocy niestandardowej](https://github.com/microsoft/dynamics356f-o-custom-help)  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
