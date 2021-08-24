---
title: Wprowadzanie umiejętności
description: Pracownicy i kierownicy mogą wprowadzać umiejętności w Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c2a35079f43b92b5ff6d68aa7068f3e1f68ce8c2c32d23cdd22798f95c9a0ff4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732232"
---
# <a name="enter-skills"></a>Wprowadzanie umiejętności

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Można wprowadzić umiejętności docelowe lub rzeczywiste umiejętności pracowników, kandydatów lub osób kontaktowych w Dynamics 365 Human Resources. Umiejętność docelowa jest umiejętnością, jaką osoba planuje zdobyć. Rzeczywista umiejętność jest umiejętnością, jaką dana osoba aktualnie dysponuje.

## <a name="create-a-workflow-to-auto-approve-skills"></a>Tworzenie przepływu pracy w celu automatycznego zatwierdzania umiejętności

Aby wprowadzić umiejętności bez konieczności ich zatwierdzania, należy stworzyć przepływ pracy, który będzie automatycznie zatwierdzał umiejętności.

> [!NOTE]
> Umiejętności wprowadzane przez pracowników zawsze wymagają zatwierdzenia przez kierownika. Ten przepływ pracy automatycznie zatwierdza jedynie umiejętności wprowadzone przez menedżerów w imieniu swoich pracowników.

1. W obszarze roboczym **Zarządzanie personelem** wybierz **Łącza**.

2. W obszarze **Konfiguracja** wybierz opcję **Przepływy pracy modułu zasobów ludzkich**.

3. Wybierz pozycję **Nowy**.

4. W okienku **Utwórz przepływpracy** wybierz opcję **Umiejętności pracownika**.

   [![Wybierz przepływ pracy umiejętności pracownika.](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)

5. W okienku **Otworzyć ten plik?** należy wybrać **Otwórz**. Po wyświetleniu monitu wprowadź swoje dane uwierzytelniające.

6. W edytorze przepływu pracy wybierz element **Zatwierdź umiejętności** i przeciągnij go na kanwę.

   [![Wybierz element Zatwierdź przepływ pracy umiejętności.](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)

7. Połącz element **Rozpoczęcie** z elementem **Zatwierdź umiejętności 1**, a następnie połącz element **Zatwierdź umiejętności 1** z elementem **Zakończ**. Może być konieczne przewiniecie w dół, aby zobaczyć element **Koniec**. Możesz przeciągnąć go bliżej innych elementów.

   [![Łączenie elementów przepływu pracy.](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)

8. Kliknij dwukrotnie element przepływu pracy **Zatwierdź kwalifikacje 1**, a następnie kliknij prawym przyciskiem myszy element **Krok 1**. Kliknij prawym przyciskiem myszy element **Krok 1**, a następnie wybierz polecenie **Właściwości**.

9. W oknie **Właściwości** wybierz **Warunek** na pasku z lewej strony.

10. Wybierz opcję **Wykonaj ten krok, tylko jeśli zostanie spełniony następujący warunek**.

11. Wybierz **Dodaj warunek**. Po wybraniu opcji **Gdzie** wybierz **Umiejętności samoobsługi pracownika**, a następnie wybierz **Umiejętności samoobsługi pracownika.Osoba**. Po zaznaczeniu **jest**, wybierz **pole**, a następnie **Stosunek użytkownika do osoby.Osoba**.

    [![Określ warunek.](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)

12. Wybierz pozycję **Przypisanie** na pasku adresu z lewej strony.

13. Na karcie **Typ przypisania** wybierz pozycję **Hierarchia**.

14. Na karcie **Wybór hierarchii** w polu **Typ hierarchii** wybierz pozycję **Hierarchia menedżerska**.

    [![Określ hierarchię menedżerską.](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)

15. Wybierz opcję **Zamknij**, wybierz **Przepływ pracy** w kanwie modułu nawigacyjnego, a następnie wybierz polecenie **Zapisz i zamknij**.

Więcej informacji na temat tworzenia przepływów pracy zawiera temat [Omówienie tworzenia przepływów pracy](../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md?toc=/dynamics365/human-resources/toc.json).

## <a name="enter-skills-for-a-worker"></a>Wprowadzanie umiejętności pracownika

1. Wybierz pracownika.

2. Na pasku akcji strony **Pracownik** wybierz pozycję **Osoba**, a następnie wybierz pozycję **Umiejętności**.

3. Na stronie **Umiejętności** wypełnij następujące pola dla każdej umiejętności:

   - **Umiejętność**: wybierz daną umiejętność.
   - **Poziom**: wybierz wartość **Rzeczywista** dla umiejętności, która jest już posiadana przez pracownika, lub wybierz pozycję **Docelowa** dla umiejętności, nad którą pracownik pracuje.
   - **Poziom**: wybierz poziom kwalifikacji pracownika.
   - **Data zdobycia poziomu**: aby wybrać datę, należy kliknąć datę w kalendarzu.
   - **Egzaminator**: w razie potrzeby wybierz z listy kandydata. Wyszukiwanie można filtrować.
   - **Lata doświadczenia**: wprowadź lata doświadczenia.
   - **Zweryfikowano**: jeśli umiejętność została zweryfikowana, zaznacz pole.
   - **Zweryfikowane przez**: wprowadź nazwę weryfikatora.

4. Po wprowadzeniu umiejętności wybierz przycisk **Zapisz**.

## <a name="see-also"></a>Informacje dodatkowe

[Konfigurowanie umiejętności](hr-develop-skills.md)<br>
[Mapowanie umiejętności](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]