---
title: Planowanie rozmów kwalifikacyjnych i informacji zwrotnych
description: W tym temacie omówiono działania planowania rozmów kwalifikacyjnych i wysyłania informacji zwrotnych w Attract.
author: ''
manager: AnnBe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.search.region: Global
ms.author: hasrivas
ms.openlocfilehash: 7bc5a66bb221cb0ab2c69fcb1013ed48a7c664a6
ms.sourcegitcommit: 1e32d78868098fd76124bb41363f15c4ec3ea15a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2019
ms.locfileid: "374961"
---
# <a name="interview-scheduling-and-feedback"></a>Planowanie rozmów kwalifikacyjnych i informacji zwrotnych

[!include[banner](../includes/banner.md)]

## <a name="scheduler-activity"></a>Działanie Harmonogram

Działanie harmonogramu są opcjonalne i składa się z dwóch składników: Pytanie o dostępność kandydata oraz Harmonogram. Składnik Dostępność kandydata umożliwia wysyłanie wiadomości e-mail w celu sprawdzenia dostępności kandydata. Składnik Harmonogram umożliwia planowanie rozmów kwalifikacyjnych z udziałem kandydata i zespołu rekrutacyjnego.

### <a name="candidate-availability-request"></a>Pytanie o dostępność kandydata

Aby wysłać wiadomości e-mail do kandydatów z pytaniem o ich dostępność, zaznacz pole **Zażądaj dostępności kandydata**. Jeśli to pole nie jest zaznaczone, ten krok nie będzie wyświetlany w procesie rekrutacji na to stanowisko.

Aby wysłać żądanie dostępności, kliknij przycisk **Wyślij żądanie**, wybierz dostępne daty i szablon wiadomości e-mail, a następnie wyślij wiadomości e-mail do kandydata.

[![Widok rekrutera Attract do wysyłania pytania o dostępność kandydata](./media/scheduler-candidate-request.png)](./media/scheduler-candidate-request.png)

Kiedy kandydat otrzyma wiadomość e-mail, aby odpowiedzieć na żądanie, może zalogować się do portalu kandydatów, wybrać odpowiednią datę dostępności, a następnie kliknąć przycisk **Prześlij**.

### <a name="schedule"></a>Harmonogram
Istnieje kilka konfiguracji harmonogramu rozmów kwalifikacyjnych służących do szybkiego tworzenia i wysyłania pętli rozmowy kwalifikacyjnej do osób prowadzących rozmowę kwalifikacyjną i kandydatów.

1. Kliknij przycisk **Utwórz harmonogram** i w polu **Dodawanie osób prowadzących rozmowę kwalifikacyjną** wyświetl listę wszystkich kandydatów, którzy mają być objęci pętlą rozmowy kwalifikacyjnej.
[![Widok rekrutera Attract do rozpoczynania tworzenia harmonogramu pętli rozmowy kwalifikacyjnej](./media/schedule-start-over.png)](./media/schedule-start-over.png)   
    Jeśli kandydat odpowiedział na pytanie o dostępność do rozmowy kwalifikacyjnej, pole **Data rozmowy kwalifikacyjnej** zostanie wstępnie wypełnione w momencie wybrania. W razie potrzeby można wybrać inną datę.
    
    W przypadku wybrania pola **Ustaw jako panelową rozmowę kwalifikacyjną** grupa osób prowadzących rozmowę kwalifikacyjną po lewej stronie jest przesuwana do pętli pojedynczego panelu w celu utworzenia rozmowy kwalifikacyjnej. Należy następnie zdefiniować określoną sekwencję rozmów kwalifikacyjnych.
    
    Harmonogram rozmów kwalifikacyjnych powinien być ułożony w taki sposób, aby był najlepiej dopasowany do dostępności uczestników. W przypadku kandydata wewnętrznego można uwzględnić jego dostępność w ramach zaleceń harmonogramu.
    
    Aby zorganizować spotkanie online, zaznacz pole **Dodaj spotkania w aplikacji Skype**; wówczas każde zdarzenie rozmowy kwalifikacyjnej będą miało dostępne łącze **Skype dla firm**.

2. Wybierz czas trwania rozmowy kwalifikacyjnej dla każdego zdarzenia rozmowy kwalifikacyjnej, a następnie kliknij przycisk **OK**, aby rozpocząć tworzenie harmonogramu.

    Jeśli wybrana jest opcja **Zalecenia**, będą wyświetlane sugestie, a siatka rozmowy kwalifikacyjnej zostanie wstępnie wypełniona. Można wyświetlić bieżący kalendarz dostępności wszystkich znaczonego osób prowadzących rozmowę kwalifikacyjną. Ponadto można wyświetlać kalendarz kandydata, jeśli jest on wewnętrznym kandydatem.

3. Jeśli nie dostępnych sugestii, w kolumnie **Rozmowy kwalifikacyjne**kliknij przedział czasowy, podaj tytuł rozmowy kwalifikacyjnej, szczegóły i wypełnij szczegóły lokalizacji, w razie potrzeby. Do rozmowy kwalifikacyjnej można dodać łącze programu **Skype dla firm**.

4. Aby uwzględnić dodatkowe osoby przeprowadzające rozmowy kwalifikacyjne, kliknij kolumnę siatki **Dodaj osobę przeprowadzającą rozmowę kwalifikacyjną**, aby wybrac jedną lub więcej osób przeprowadzających rozmowy kwalifikacyjne. Aby usunąć rozmowę kwalifikacyjną z pętli można użyć opcji wielokropka (...).
    
5. Jeśli rozmowy kwalifikacyjne są zaplanowane w innej strefie czasowej, wybierz wymagane miasto/strefę czasową z listy rozwijanej w prawym górnym rogu. Siatka dostępności osoby prowadzącej rozmowę kwalifikacyjną zostanie zaktualizowana do nowej strefy czasowej. Wybrana strefa czasowa będzie teraz również wyświetlana w widoku **Podsumowanie rozmowy kwalifikacyjnej**, który jest wspólny dla osoby prowadzącej rozmowę kwalifikacyjną i kandydata. 

6. Kliknij przycisk **Wyślij do osób prowadzących rozmowę kwalifikacyjną**, aby wysłać zaproszenia na spotkanie do zaangażowanych osób prowadzących rozmowę kwalifikacyjną.

    Po wysłaniu żądania rozmowy kwalifikacyjnej do kandydatów, mogą oni odpowiedzieć bezpośrednio z poziomu otrzymanej wiadomości e-mail z zaproszeniem.

    >[!NOTE]
    > W przypadku wszystkich rozmów 1:1 przypomnienia są wysyłane do osób prowadzących rozmowę kwalifikacyjną co 24 godziny, jeśli osoba prowadząca rozmowę nie odpowiedziała (nie zaakceptowała ani nie odrzuciła) żądania rozmowy kwalifikacyjnej.

    > W przypadku wszystkich rozmów grupowych nie ma automatycznych przypomnień o żądaniu rozmowy kwalifikacyjnej. Aby ręcznie wyzwolić przypomnienie, edytuj rozmowę kwalifikacyjną i użyj opcji **Aktualizuj & wyślij**, aby odesłać żądanie do osób prowadzących rozmowę kwalifikacyjną.

    Odpowiedzi osób prowadzących rozmowę kwalifikacyjną są rejestrowane i wyświetlane w Attract. Jeśli osoba prowadząca rozmowę kwalifikacyjną odrzuci zaproszenie, otrzymasz powiadomienie o konieczności wprowadzenia zmiany. Aby wyświetlić odpowiedź w widoku siatki **Harmonogram**kliknij ikonę dymka.

[![Widok rekrutera odpowiedzi osoby prowadzącej rozmowę kwalifikacyjną](./media/schedule-interviewer-response.png)](./media/schedule-interviewer-response.png)

7. Gdy harmonogramu rozmowy kwalifikacyjnej jest gotowy do udostępnienia kandydatowi, kliknij **Wyślij do kandydata**. Imiona i nazwiska osób prowadzących rozmowę kwalifikacyjną oraz przedziały czasu mogą być widoczne dla kandydatów lub ukryte.

8. Wybierz szablon e-mail i wyślij kandydatowi podsumowanie rozmowy kwalifikacyjnej. Kandydat może wyświetlić te informacje w wiadomości e-mail i w portalu kandydatów.
    
>[!NOTE] 
> Dostępność w kalendarzu kandydata jest wyświetlana tylko wtedy, jeśli kandydat jest wewnętrzny. Podobnie tylko wewnętrzni kandydaci mogą być używani do ulepszania zaleceń harmonogramu rozmowy kwalifikacyjnej. Obecnie kandydaci (zewnętrzni lub wewnętrzni) nie otrzymują wiadomości e-mail z zaproszeniem na spotkanie, natomiast kandydat otrzymuje tylko podsumowanie rozmów kwalifikacyjnych.

## <a name="feedback-activity"></a>Działanie Opinia

Opinie są opcjonalne w szablonie stanowisk. Umożliwia ono wprowadzanie rekomendacji dotyczących kandydata lub komentarzy z opiniami przez uczestników rozmowy kwalifikacyjnej. Jeśli pole **Dziedzicz współtwórców opinii z zespołu rekrutacyjnego** jest zaznaczone, osoba rekrutująca, menedżer zatrudniający i osoby przeprowadzające rozmowy kwalifikacyjne są automatycznie dodawane do działania Opinia. Organizacje mogą również zezwalać osobom przeprowadzającym rozmowy kwalifikacyjne na przeglądanie opinii innych osób, zanim prześlą swoje własne opinie. Organizacje mogą także pozwalać osobom przeprowadzającym rozmowy kwalifikacyjne na edytowanie już przesłanych opinii. Zaleca się, aby osoby prowadzące rozmowę kwalifikacyjną przesłały opinię na temat ostatnio przeprowadzonych rozmów kwalifikacyjnych na podstawie aktualnej konfiguracji w ramach szablonu stanowisk. Menedżer zatrudniający lub rekruter na stanowisko może również ręcznie przypominać osobom prowadzącym rozmowy kwalifikacyjne o przesłaniu opinii.

## <a name="interview-activity"></a>Działanie Rozmowa kwalifikacyjna

Działanie rozmowy kwalifikacyjnej jest opcjonalne w trzech komponentach: Pytanie o dostępność kandydata, Harmonogram oraz Opinia. Użyj działania rozmowy kwalifikacyjnej w szablonie zadania, jeśli chcesz uwzględnić wszystkie pytania o dostępność kandydata, harmonogram i informacje zwrotnych w ramach procesu zamiast używać ich osobno w trakcie zatrudnienia.
