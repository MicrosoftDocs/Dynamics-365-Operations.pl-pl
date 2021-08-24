---
title: Konfigurowanie umiejętności
description: Umiejętności pracownika można śledzić w Dynamics 365 Human Resources. Można również określić umiejętności, które są wymagane dla danego zadania.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a8025dd4000a3678e7f7eb7faebfa45852f0054570a2948dadbc21913c63f578
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732160"
---
# <a name="configure-skills"></a>Konfigurowanie umiejętności

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Umiejętności pracownika można śledzić w Dynamics 365 Human Resources. Można również określić umiejętności, które są wymagane dla danego zadania.

Przykłady umiejętności, które można śledzić:

- Kierownicze — zdolność do nadzorowania pracy innych.
- Przywódcze — zdolność do kierowania pracownikami i domenami biznesowymi.
- Planowania — zdolność do patrzenia w przyszłość, formułowania wizji i doprowadzania ich do końca.
- HTML — umożliwia zapis kodu HTML.

Jeśli nie masz jeszcze skonfigurowanych typów umiejętności i modeli oceniania, musisz je dodać przed utworzeniem umiejętności.

Następujące osoby mogą wprowadzić umiejętności dla pracownika:

- Pracownicy mogą sami wprowadzać swoje umiejętności w ramach samoobsługi pracowniczej. Umiejętności te wymagają zatwierdzenia przez kierownika.
- Menedżerowie mogą wprowadzać umiejętności dla swoich pracowników. Można utworzyć przepływ pracy, który będzie automatycznie zatwierdzał te umiejętności.

## <a name="create-a-skill-type"></a>Tworzenie typu umiejętności

Typy umiejętności to kategorie, do których należą poszczególne umiejętności, takie jak Administracja czy Sprzedaż.

1. W obszarze roboczym **Rozwój pracowników** wybierz opcję **Łącza**.

2. W obszarze **Ustawienia umiejętności** wybierz **Typy umiejętności**.

3. Wybierz pozycję **Nowy**.

4. Wypełnij następujące pola:

   - **Typ umiejętności** – Wprowadź nazwę typu umiejętności.
   - **Opis** – Wprowadź opis typu umiejętności.

5. Wybierz opcję **Zapisz**.

## <a name="create-a-rating-model"></a>Utwórz model oceny

Modele oceniania pomagają w ocenie rzeczywistego poziomu umiejętności danej osoby, poziom, do osiągnięcia jakiego powinna ona dążyć lub poziom umiejętności wymagany dla zadania. Każdy poziom w modelu oceniania ma przypisany współczynnik.

1. W obszarze roboczym **Rozwój pracowników** wybierz opcję **Łącza**.

2. W obszarze **Ustawienia umiejętności** wybierz pozycję **Modele oceniania**.

3. Wybierz pozycję **Nowy**.

4. Wypełnij następujące pola:

   - **Ocena**: wprowadź nazwę modelu oceniania, na przykład **Umiejętności**.
   - **Opis**: służy do wprowadzania opisu modelu oceniania, takiego jak **Umiejętności**.

5. W sekcji **Poziomy** wybierz pozycję **Nowy**. Dla każdego poziomu, który chcesz dodać, wypełnij następujące pola:

   - **Poziom**: Umożliwia wprowadzenie nazwy poziomu.
   - **Opis**: Umożliwia wprowadzenie opisu poziomu.
   - **Współczynnik**: należy wprowadzić wartość współczynnika od 0–9. Czynniki pomagają znormalizować wyniki umiejętności, które wykorzystują różne modele oceny. Każdy poziom musi mieć unikalny czynnik. Poziomy z wysokimi wartościami współczynników mają większą wagę w modelu oceniania.

   W razie potrzeby kontynuuj dodawanie poziomów. Dla każdego modelu oceny można wprowadzić do 10 poziomów.

6. Wybierz opcję **Zapisz**.

## <a name="create-a-skill"></a>Tworzenie umiejętności

Przed przypisaniem umiejętności, utworzeniem przeszukiwania mapowania umiejętności lub profilu umiejętności, należy wprowadzić informacje o umiejętnościach na stronie **Umiejętności**. Dla każdej umiejętności można wybrać typ umiejętności i model oceniania.

1. W obszarze roboczym **Rozwój pracowników** wybierz opcję **Łącza**.

2. W obszarze **Ustawienia umiejętności** wybierz **Umiejętności**.

3. Wybierz pozycję **Nowy**.

4. Wypełnij następujące pola:

   - **Umiejętność** – Wprowadź nazwę umiejętności.
   - **Opis** – Wprowadź opis umiejętności.
   - **Ocena**: Umożliwia wybór modelu oceny, który ma być stosowany w ocenie umiejętności.
   - **Typ umiejętności**: umożliwia wybór z listy typów umiejętności.

5. Wybierz opcję **Zapisz**.

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzanie umiejętności](hr-develop-enter-skills.md)<br>
[Mapowanie umiejętności](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]