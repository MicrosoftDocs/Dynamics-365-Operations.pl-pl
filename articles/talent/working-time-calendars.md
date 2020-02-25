---
title: Kalendarze czasu pracy
description: W tym temacie opisano funkcjonalność kalendarzy czasu pracy w programie Dynamics 365 Human Resources oraz sposób konfigurowania kalendarzy.
author: andreabichsel
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: ac19fca407bd936cb9b7edcfa9f4eb81daf607dd
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006225"
---
# <a name="working-time-calendars"></a>Kalendarze czasu pracy

Funkcja kalendarza czasu pracy pozwala utworzyć kalendarz z godzinami i dniami, kiedy pracownicy pracują w organizacji. Kalendarze usprawniają obsługę wniosków o czas wolny dzięki domyślnemu rozpoznawaniu godzin i dni. Gdy pracownik przesyła wniosek o czas wolny, nie musi się martwić o święta i dni wolne od pracy, ponieważ automatycznie zarządza tym kalendarz czasu pracy.

## <a name="setting-up-a-working-time-calendar"></a>Konfigurowanie kalendarza czasu pracy

Kalendarze zawierają informacje o generowaniu, wnioskowanych dniach i godzinach, dniach kalendarzowych, czasach pracy w dniach oraz zarejestrowanych pracownikach. 

Aby skonfigurować kalendarz, należy wykonać następujące czynności:

1. Na stronie **Administrowanie organizacją** kliknij opcję **Kalendarze**.

2. W okienku akcji kliknij przycisk **Nowy**, a następnie wprowadź nazwę i opis.

3. Wybierz dni pracy w organizacji i wprowadź czas pracy.

4. Dodaj święta i dni wolne od pracy za pomocą przycisku **Dodaj**.

5. Wprowadź nazwę i opis dla świąt i dni wolnych od pracy, taką jak Święta amerykańskie lub Dni wolne. Wprowadź daty świąt i dni wolnych od pracy. Zapisz listę świąt i dni wolnych od pracy, a następnie zamknij stronę.

6. Wybierz listę świąt i dni wolnych od pracy z menu rozwijanego.

7. Jeśli pracownicy mają standardowo przewidziany czas wolny od pracy, na przykład przerwy na obiady i odpoczynek, dodaj je również. Zaznacz opcję **Czas wolny od pracy**, a następnie wprowadź nazwę i przedział czasu. Zamknij stronę. 

8. Kliknij przycisk **Dodaj**, aby dodać czas wolny od pracy do kalendarza.

9. Na karcie **Dni** wybierz opcję **Generuj**, aby wygenerować dni w kalendarzu. Wprowadź przedział dat kalendarza. Dni i czasy pracy zostaną wygenerowane na podstawie dni i czasów pracy zdefiniowanych w opcjach generowania powiązanych z wybranymi datami.

10. Aby przypisać kalendarz do pracowników, w okienku akcji wybierz opcję **Przypisz do pracowników etatowych**. Zaznacz pracowników, którym chcesz przypisać ten kalendarz, i kliknij przycisk **Przypisz**.

Pracownicy nie muszą mieć przypisanych kalendarzy. Jeśli zdefiniowano kalendarz czasu pracy, dni wolne są automatycznie wykluczane z wniosku o czas wolny. Ilość w godzinach lub dniach jest domyślnie ustawiana według czasów pracy określonych w kalendarzu. Jeśli pracownik nie ma przypisanego kalendarza, wszystkie dni są dostępne dla przyznania czasu wolnego, a ilość czasu wolnego nie jest domyślna dla wniosku. 
