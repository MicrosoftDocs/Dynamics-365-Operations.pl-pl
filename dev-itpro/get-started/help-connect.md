---
title: "Łączenie z systemem Pomocy"
description: "W tym temacie opisano składniki systemu Pomocy w programie Microsoft Dynamics 365 for Operations, sposoby ich podłączania oraz podstawowe zasady tworzenia pomocy niestandardowej."
author: margoc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 5ac5e30cff2239f601778001368fa7aaba478f5c
ms.lasthandoff: 03/31/2017


---

# <a name="connect-the-help-system"></a>Łączenie z systemem Pomocy

W tym temacie opisano składniki systemu pomocy Microsoft Dynamics 365 dla operacji. Omówiono w nim sposoby łączenia tych składników i krótki opis sposobu tworzenia niestandardowych pomocy. 

<a name="help-architecture"></a>Architektura modułu Pomoc
-----------------

Następująca ilustracja pokazuje części 365 Dynamics dla operacji pomocy systemu. System pomocy w produkcie ściąga artykuły z 365 Dynamics witryna operacji na https://docs.microsoft.com, a także linie pomocnicze zadania przechowywane w procesu biznesowego w cyklu życia usługi (LCS). 
**Uwaga:** funkcje wymienione na diagramie gwiazdką (\*) są planowane, ale nie są jeszcze dostępne. [![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Łączenie systemu pomocy
Za pomocą **parametrów systemu** stronę, Administratorzy systemu połączyć kawałki dla realizacji systemu pomocy. [![Formularz Parametry systemu z ustawieniami pomocy](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) na **parametrów systemu** strony, wykonaj następujące kroki:

1.  **Ważne:** przy pierwszym otwarciu **Pomoc** kartę, należy nawiązać połączenie usług cyklu eksploatacji. Pamiętaj kliknąć łącze w środku formularza, czekać na połączenie, zamknij okno dialogowe, a następnie kliknij **OK** aby dostać się do **parametrów systemu** strony. [![Nawiązać LCS](./media/connect-to-lcs-crop-1024x365.png "nawiązać LCS")](./media/connect-to-lcs-crop.png)
2.  Wybierz projekt Lifecycle Services, z którym chcesz się połączyć.
3.  Wybierz biblioteki BPM (w ramach wybranego projektu), z których będą pobierane nagrania zadań.
4.  Ustaw kolejność wyświetlania bibliotek BPM. Określa kolejność wyświetlania nagrań z bibliotek w okienku **pomocy**.

Po wykonaniu tych kroków można otworzyć okienko **pomocy** i kliknąć kartę **Przewodniki po zadaniach**. Teraz widać przewodniki po zadaniach, które mają zastosowanie do strony aktualnie wyświetlanej w programie Dynamics 365 for Operations. Jeśli nie zostaną znalezione żadne przewodniki po zadaniach, możesz wprowadzić słowa kluczowe, aby doprecyzować wyszukiwanie.

### <a name="showing-translated-task-guides"></a>Wyświetlanie przetłumaczonych przewodników po zadaniach

Przewodniki przetłumaczony zadania były po raz pierwszy wysłane w 2016 maja Unified biblioteki APQC i biblioteki wprowadzenie. Aby wyświetlić przetłumaczone przewodniki po zadaniach w pomocy w programie Dynamics 365 for Operations, upewnij się, że masz połączenie z biblioteką z maja. Język, w którym przewodnik zadanie zostanie wyświetlone w steruje dla każdego użytkownika, ustawienia języka w obszarze **opcje**&gt;**preferencje**. **Uwaga:** Mimo że przetłumaczono wiele przewodników po zadaniach, obecnie klient programu Dynamics 365 for Operations nie pokazuje nazw przetłumaczonych przewodników. Ponadto prowadnice zadań, które zostały wydane w lutym 2016 są dostępne w tłumaczeniu w bibliotece maja. Opublikujemy zaktualizowaną bibliotekę z dodatkowymi tłumaczeniami.

-   Jeśli przewodnik po zadaniu został przetłumaczony, po otwarciu przewodnika jego cały tekst będzie wyświetlany w wybranym języku.
-   Jeśli przewodnik po zadaniu nie został jeszcze przetłumaczony, po otwarciu przewodnika tylko część tekstu (formanty) będzie wyświetlana w wybranym języku.

## <a name="creating-custom-help"></a>Tworzenie pomocy niestandardowej
We wdrożeniu programu Dynamics 365 for Operations można utworzyć pomoc niestandardową poprzez utworzenie nagrań zadań odpowiadających konkretnemu wdrożeniu i zapisanie ich w bibliotece procesów biznesowych LCS. W przypadku partnerów: jeśli zostanie podniesiony poziom biblioteki do firmowej i zostanie ona uwzględniona w rozwiązaniu, będzie dostępna dla klientów. Można również utworzyć kopię ujednoliconej globalnej biblioteki APQC, a następnie otworzyć tę kopię, otwierać z niej nagrania zadań, modyfikować je i zapisywać nagrania z wprowadzonymi zmianami. Aby uzyskać więcej informacji, zobacz [jak utworzyć zadanie nagrania, aby użyć jako dokumentacji lub szkolenia](../user-interface/task-recorder.md).

<a name="see-also"></a>Informacje dodatkowe
--------

[Help overview](help-overview.md)

[Omówienie Rejestratora zadań](../user-interface/task-recorder.md)

[Jak utworzyć nagrania zadań do użycia w dokumentacji lub na szkoleniach](../user-interface/task-recorder-training-docs.md)

[Tworzenie nowej biblioteki szkolenia dla usługi Dynamics 365 dla operacji w ramach cyklu życia usługi za pomocą programu Task Recorder (łącze zewnętrzne)](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)


