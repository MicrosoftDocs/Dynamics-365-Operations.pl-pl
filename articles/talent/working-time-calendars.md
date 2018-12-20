---
title: Kalendarze czasu pracy
description: "W tym temacie opisano funkcjonalność kalendarzy czasu pracy w programie Dynamics 365 for Talent Core HR oraz sposób konfigurowania kalendarzy."
author: jcart1106
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2018-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 1bf37d65cd8ce6a98fc2d2fb11ae9587cf6958a3
ms.openlocfilehash: 2465065d7db18a5468d7c979e0d6cb9c7e76f969
ms.contentlocale: pl-pl
ms.lasthandoff: 09/27/2018

---

# <a name="working-time-calendars"></a>Kalendarze czasu pracy

[!include [banner](includes/banner.md)]

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
