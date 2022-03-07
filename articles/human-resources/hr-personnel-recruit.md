---
title: Rekrutowanie kandydatów
description: Ten temat dotyczy sposobu rekrutacji kandydatów w Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 77d37cba84fcd6fb8f93da79b10db2db91d91db0
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066607"
---
# <a name="recruit-job-candidates"></a>Rekrutowanie kandydatów


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources ułatwia zarządzanie wnioskami o rekrutację. Usprawnia również przejście od kandydata do pracownika. Jeśli Twoja organizacja korzysta z oddzielnej aplikacji do rekrutacji, proces rekrutacji może obejmować następujące kroki:

- Wprowadzanie wniosku o rekrutację w module Human Resources.
- Przekazywanie polecanych kandydatów do modułu Human Resources z aplikacji do rekrutacji.
- Zakończenie procesu zatwierdzania kandydata w module Human Resources.

W przypadku braku oddzielnej aplikacji do rekrutacji kandydatami w module Human Resources można również zarządzać ręcznie.

> [!NOTE]
> Jeśli jesteś administratorem lub deweloperem i chcesz zintegrować moduł Human Resources z aplikacją do rekrutacji innego producenta, zobacz [Konfigurowanie integracji usługi Dataverse](hr-admin-integration-common-data-service.md) i [Konfigurowanie tabel wirtualnych usługi Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)
>
> Aplikacje do integracji rekrutacji można również znaleźć na stronie [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).
>
## <a name="enable-recruiting-requests"></a>Włącz wnioski o rekrutację

Aby przesyłać wnioski o rekrutację w module Human Resources, należy najpierw włączyć tę funkcję w **Udostępnionych parametrach modułu Human Resources**.

1. W obszarze roboczym **Zarządzanie personelem** wybierz **Łącza**.
2. W obszarze **Konfiguracja** wybierz opcję **Udostępniane parametry zasobów ludzkich**.
3. Na karcie **Rekrutacja** w obszarze **Rekrutacja** przy opcji **Włącz wnioski o rekrutację** ustaw **Tak**.

## <a name="add-a-recruiting-request-location"></a>Dodawanie lokalizacji wniosku o rekrutację

Jeśli organizacja ma wiele lokalizacji, można je dodać, tak aby wnioskodawca mógł wybrać lokalizację, w której będzie pracowała nowa osoba. Lokalizacja zostanie uwzględniona w publikacji oferty pracy.

1. Na pasku wyszukiwania wprowadź **lokalizację wniosku o rekrutację**.
2. Wybierz pozycję **Nowy**.
3. W polu **Lokalizacja wniosku o rekrutację** wprowadź nazwę lokalizacji.

    ![Dodawanie lokalizacji wniosku o rekrutację.](./media/hr-recruit-0a-add-location.png)

4. W polu **Opis** wprowadź opis lokalizacji.
5. W obszarze **Lokalizacja** wybierz **Dodaj**. Jeśli pojawi się okno **Nowy adres**, wprowadź adres lokalizacji.

    ![Wprowadź adres.](./media/hr-recruit-0b-address.png)

6. W obszarze **Informacje kontaktowe** wprowadź dane osoby do kontaktu w tej lokalizacji.
7. Wybierz opcję **Zapisz**.

## <a name="add-a-recruiting-request"></a>Dodawanie wniosku o rekrutację

Menedżerowie mogą przesyłać wnioski o rekrutację w module Human Resources. W przypadku korzystania z oddzielnej aplikacji do rekrutacji wykonanie tych kroków spowoduje wysłanie wniosku o rekrutację i rozpoczęcie procesu rekrutacji w tej aplikacji. W przeciwnym razie procedura ta po prostu rozpocznie wewnętrzny proces rekrutacji.

1. Wybierz opcję **Samoobsługa pracownika etatowego**.
2. Wybierz kartę **Mój zespół**.
3. Wybierz **Złóż wniosek o rekrutację**.

    ![Uruchamianie wniosku o rekrutację.](./media/hr-recruit-1-request-to-recruit.png)

4. Wypełnij pola **Opis**, **Stanowisko** i **Szacowana data rozpoczęcia**.

    ![Zakończenie tworzenia wniosku o rekrutację.](./media/hr-recruit-2-request-to-recruit.png)

5. Kliknij przycisk **Kontynuuj**. Wniosek o rekrutację na dane stanowisko zostanie utworzony.
6. W obszarze **Ogólne** wybierz osobę rekrutującą z listy rozwijanej **Osoba rekrutująca**, a następnie wybierz lokalizację z listy rozwijanej **Lokalizacja wniosku o rekrutację**.
7. W obszarze **Stanowisko** zmień informacje zależnie od potrzeb, a następnie wybierz opcję **Utwórz szczegóły ze stanowiska**.

    ![Utwórz szczegóły ze stanowiska.](./media/hr-recruit-3-create-details-from-job.png)

    Pozostała część wniosku o rekrutację zostanie wypełniona domyślnymi informacjami dotyczącymi danego stanowiska.

8. W obszarze **Zewnętrzny opis** wprowadź opis stanowiska do udostępnienia poza firmą.
9. W obszarze **Stanowiska** wybierz opcję **Dodaj**, a następnie wybierz stanowisko dla danego wniosku o rekrutację.

    ![Dodawanie stanowiska.](./media/hr-recruit-4-select-position.png)

10. W obszarze **Umiejętności** wybierz opcję **Dodaj**, a następnie wybierz umiejętność.
11. W obszarze **Wymagane wykształcenie** wybierz opcję **Dodaj**, a następnie wybierz wartości z list rozwijanych **Wykształcenie** i **Poziom wykształcenia**.

    ![Dodawanie wymagań dotyczących wykształcenia.](./media/hr-recruit-5-select-educational-requirements.png)

12. W obszarze **Komentarz** dodaj opcjonalne uwagi.
13. W obszarze **Wynagrodzenie** wybierz poziom z listy rozwijanej **Poziom**, a następnie odpowiednio dostosuj **Próg niski**, **Punkt kontrolny** i **Próg wysoki**.
14. Gdy wniosek o rekrutację będzie gotowy i można rozpocząć proces rekrutacji, wybierz opcję **Uaktywnij** na pasku menu.

    ![Aktywacja wniosku o rekrutację.](./media/hr-recruit-6-activate-recruit-request.png)

15. Wybierz opcję **Zapisz**.

## <a name="view-and-edit-your-recruiting-requests"></a>Wyświetlanie i edytowanie wniosków o rekrutację

Jeśli jesteś menedżerem i chcesz wyświetlić swoje własne wnioski:

1. Wybierz opcję **Samoobsługa pracownika etatowego**.
2. Wybierz kartę **Mój zespół**.
3. W obszarze **Informacje dotyczące mojego zespołu** wybierz kartę **Wnioski o rekrutację**.

    ![Wybierz kartę Wnioski o rekrutację.](./media/hr-recruit-7-recruiting-requests.png)

4. Aby wyświetlić lub edytować wniosek o rekrutację, należy wybrać go z tabeli.

Jeśli jesteś pracownikiem działu kadr i chcesz przejrzeć wszystkie wnioski o rekrutację:

1. Wybierz **Zarządzanie personelem**.
2. Wybierz **Wnioski o rekrutację**.

    ![Wyświetlanie wniosków o rekrutację na stronie Zarządzanie personelem.](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. Aby wyświetlić lub edytować wniosek o rekrutację, należy wybrać go z tabeli.

## <a name="add-or-edit-a-candidate-profile"></a>Dodawanie lub edytowanie profilu kandydata

Jeśli zarządzanie wnioskami o rekrutację zostało zintegrowane z inną aplikacją, to wnioski są przekazywane do tej aplikacji. Następnie aplikacja do rekrutacji wysyła informacje o kandydatach do modułu Human Resources. W przeciwnym razie możesz postępować zgodnie z wewnętrznym procesem rekrutacji oraz wprowadzać dane kandydatów ręcznie.

1. Wybierz **Zarządzanie personelem**.
2. Wybierz **Łącza**.
3. W obszarze **Rekrutacja** wybierz opcję **Kandydaci**.

    ![Wyświetlanie kandydatów.](./media/hr-recruit-9-candidates.png)

4. Aby dodać kandydata, wybierz opcję **Nowy**. Aby edytować dane istniejącego kandydata, wybierz go z listy i wybierz opcję **Edytuj**. Zostanie wyświetlony profil kandydata.
5. W obszarze **Podsumowanie dotyczące kandydata** wprowadź lub zmień odpowiednie dane kandydatów.
6. W obszarze **Wniosek o rekrutację** wybierz wniosek o rekrutację, z którym ma być połączony kandydat. Następnie wypełnij pola **Szacunkowa data rozpoczęcia**, **Menedżer zatrudniający**, **Stanowisko** i **Opis**.

    ![Łączenie z wnioskiem o rekrutację.](./media/hr-recruit-10-link-to-recruiting-request.png)

7. Uzupełnij wszystkie informacje w następujących obszarach, które chcesz uwzględnić w rekordzie kandydata:

    - **Komentarze**
    - **Doświadczenie zawodowe**
    - **Informacje o kontakcie**
    - **Wykształcenie**
    - **Umiejętności**
    - **Certyfikaty**
    - **Kontrole**

8. Wybierz opcję **Zapisz**.

## <a name="hire-a-candidate"></a>Zatrudnianie kandydata

Gdy firma jest gotowa do zatrudnienia kandydata, wykonaj poniższe kroki, aby zmienić kandydata w pracownika etatowego.

1. Na stronie **kandydata** wybierz **Zatrudnij**.

    ![Zatrudnianie kandydata.](./media/hr-recruit-11-hire.png)

2. Wypełnij wszystkie pola na stronie **Zatrudnij nowego pracownika** w obszarze **Szczegóły**.

    ![Wprowadzanie danych dotyczących zatrudnianej osoby.](./media/hr-recruit-12-hire-new-worker.png)

3. Sprawdź dane w obszarze **Szczegóły dotyczące stanowiska** i zmodyfikuj je w razie potrzeby.
4. W obszarze **Listy kontrolne wdrażania do pracy** wybierz odpowiednie listy kontrolne dla danego pracownika.
5. Wybierz **Kontynuuj**, aby utworzyć rekord pracownika etatowego.

    > [!NOTE]
    > W zależności od procedur w organizacji mogą być wymagane dodatkowe kroki zatwierdzania rekordu kandydata, zanim stanie się on rekordem pracownika etatowego.

## <a name="decide-not-to-hire-a-candidate"></a>Decyzja o niezatrudnianiu kandydata

W przypadku decyzji o niezatrudnianiu kandydata postępuj zgodnie z poniższą instrukcją, aby wykluczyć go z procesu weryfikacji. 

1. Na stronie **kandydata** wybierz **Nie zatrudniaj**.

    ![Niezatrudnianie kandydata.](./media/hr-recruit-13-do-not-hire.png)

2. Wybierz **Kod przyczyny** i dodaj swoje uwagi.
3. Kliknij przycisk **OK**.

## <a name="dismiss-a-candidate"></a>Odrzucanie kandydata

Jeśli zajdzie potrzeba, można odrzucić kandydata po jego zatrudnieniu. Na przykład kandydat może wycofać swoją ofertę lub nie stawić się w pracy pierwszego dnia.

- Na stronie **kandydata** wybierz **Odrzuć kandydata**.

    ![Odrzuć kandydata.](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a>Informacje dodatkowe

[Konfiguruj tabele wirtualne usługi Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Organizowanie pracowników](hr-personnel-departments-jobs-positions.md)<br>
[Konfigurowanie składników funkcji](hr-personnel-jobs.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
