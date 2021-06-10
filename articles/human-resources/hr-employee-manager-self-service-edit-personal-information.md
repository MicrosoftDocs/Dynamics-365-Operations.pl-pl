---
title: Edytuj informacje osobiste
description: W tym artykule opisano sposób edycji informacji osobistych w Samoobsłudze pracownika i menedżera.
author: andreabichsel
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2170d3b8c476fb82786721512013eae45bb78ce5
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052152"
---
# <a name="edit-personal-information"></a>Edytuj informacje osobiste

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Informacje osobiste można edytować w Dynamics 365 Human Resources w obszarze **roboczym samoobsługi pracownika etatowego**.

Informacje osobiste, które można edytować, obejmują:

- Adresy
- Informacje kontaktowe
- Kontakty osobiste
- Numery identyfikacyjne
- Metoda płatności
- Obraz używany w Human Resources

>[!NOTE]
>Możesz nie być w stanie edytować niektórych typów danych osobowych, takich jak biznesowe dane kontaktowe. Aby uzyskać więcej informacji, zobacz temat [Ogranicz edycję danych osobowych](hr-employee-self-service-restrict-editing.md).

Parametry ustawione w globalnej książce adresowej ustalają role, które mogą wyświetlać informacje osobiste użytkownika.

1. W Human Resources wybierz opcję **Samoobsługa pracownika etatowego**.

2. Wybierz opcję **Edytuj dane osobowe**.

3. Aby zmienić adres, wybierz kartę **Adresy** . Wprowadzone zmiany pojawią się w obszarze roboczym **Zarządzanie kadrami**, aby poinformować o tym dział kadr.

    - Kliknij przycisk **Dodaj**, aby dodać nowy adres.
    - Aby edytować istniejący adres, wybierz adres i wybierz opcję **Edytuj.**
    - Aby wyświetlić mapę, wybierz opcję **Mapa**.
    - Aby dodać lub usunąć kontakt, zaznacz opcję **Więcej opcji**, a następnie wybierz opcję **Zaawansowane**. W obszarze **Informacje o kontakcie** wybierz opcję **Dodaj** lub **Usuń** i w razie potrzeby zmodyfikuj odpowiednie pola.
    - Aby określić strefę czasową i lokalizację, wybierz opcję **Więcej opcji**, a następnie wybierz opcję **Zaawansowane**. W obszarze **Ogólne** edytuj pola w razie potrzeby.

4. Aby zmienić szczegóły kontaktu, wybierz kartę **Szczegóły kontaktu**. Można podać różne typy informacji kontaktowych, w tym numery telefonów, adresy e-mail i platformy społecznościowe. Można zdefiniować szczegół kontaktu jako podstawowy, ale można go określić tylko dla każdego typu jako podstawowego.

    - Kliknij przycisk **Dodaj**, aby dodać nową informację kontaktową. Odpowiednio zmodyfikuj pola.
    - Aby edytować istniejącą informację kontaktową, wybierz ją i wybierz opcję **Edytuj**. Odpowiednio zmodyfikuj pola.
    - Aby określić szczegółową osobę kontaktową jako prywatną, wybierz towar, wybierz opcję **Zaawansowane**, a następnie ustawienie przełącznika **prywatnego** na wartość **tak**. Kliknij przycisk **OK**.
      >[!NOTE]
      >Przycisk **Zaawansowane** jest niedostępny, jeśli administrator włączy funkcję **(Podgląd) Ogranicz pracownikom możliwość dodawania lub edytowania adresów i informacji kontaktowych w wybranych celach** w środowisku. Aby uzyskać więcej informacji, zobacz temat [Ogranicz edycję danych osobowych](hr-employee-self-service-restrict-editing.md).
  
5. Aby zmienić kontakty osobiste, wybierz kartę **Kontakty osobiste**. Można wyznaczyć kontakty alarmowe, beneficjentów i osoby na utrzymaniu. Kontaktem może być osoba lub organizacja. Funkcja **Zarządzania świadczeniami** korzysta z osobistych informacji kontaktowych. Aby uzyskać więcej informacji, zobacz [Konfigurowanie opcji uprawnień do kontaktu osobistego](hr-benefits-setup-contact-eligibility-options.md).

6. Aby zmienić numery identyfikacyjne, takie jak numer ubezpieczenia społecznego, wybierz kartę **Numery identyfikacyjne**. Zmiany mogą przejść proces zatwierdzania, jeśli organizacja skonfiguruje przepływ pracy zatwierdzania.

    - Aby dodać numer identyfikacyjny, wybierz **Nowe**. Wypełnij pola w razie potrzeby i wybierz **Zapisz**.
    - Aby edytować liczbę, wybierz opcję **Edytuj**. Edytuj pola w razie potrzeby i wybierz **Zapisz**.

7. Aby zmienić metody płatności, wybierz kartę **Moje informacje o płatności**. Ta karta jest dostępna tylko w przypadku włączenia metod płatności w formularzu **Parametry Human Resources**. Dział kadr może włączyć **Przekaz bankowy**, **Gotówka**, **Czek**, **Płatność elektroniczna** lub **Inne**. HR może również wyłączyć weryfikację płatności elektronicznych (używaną dla listy płac dla Stanów Zjednoczonych) oraz sprawdzanie poprawności numeru konta bankowego i marszruty.

8. Aby zmienić obraz wyświetlany w Human Resources dla Twojego profilu, wybierz kartę **Obraz** . W zależności od ustawień organizacji obrazy mogą być przekazane do zatwierdzenia.

    - Aby przekazać obraz, wybierz opcję **Przekaż nowy obraz**.
    - Aby usunąć obraz, zaznacz go, a następnie wybierz opcję **Usuń**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]