---
title: Nowy interfejs użytkownika w stylu Microsoft Office dokumentu w zarządzaniu dokumentami biznesowymi (zawiera wideo)
description: W tym temacie wyjaśniono, jak używać nowego interfejsu użytkownika w funkcji zarządzania dokumentami biznesowymi struktury raportowania elektronicznego (ER).
author: v-anamir
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e33830e2147d92ad5ee53ad11da55a50613b8ef9
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8074748"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Nowy interfejs użytkownika w stylu Microsoft Office dokumentu w zarządzaniu dokumentami biznesowymi

[!include [banner](../includes/banner.md)]

Zarządzanie dokumentami biznesowymi pozwala użytkownikom korzystać z usługi a Microsoft Office 365 lub odpowiedniej aplikacji komputerowej Microsoft Office. Edycja może obejmować zmiany projektu lub nowe wdrożenia albo użytkownicy mogą dodawać symbole zastępcze w celu dołączenia dodatkowych danych bez konieczności zmieniania kodu źródłowego. Aby uzyskać więcej informacji na temat pracy z zarządzaniem dokumentami biznesowymi, zapoznaj się z [Omówieniem zarządzania dokumentami biznesowymi](er-business-document-management.md).

Nowy interfejs użytkownika (UI) jest wyraźniejszy i wygodniejszy do używania. Obszar **Dokumenty biznesowe** pokazuje tylko te szablony, które są własnością aktualnego [aktywnego](tasks/er-configuration-provider-mark-it-active-2016-11.md) [dostawcy](general-electronic-reporting.md#Provider) i znajdują się w aktualnej instancji Dynamics 365 Finance. W poprzednim interfejsie użytkownika na karcie **Szablon** zostały wyświetlone wszystkie szablony dostępne dla dowolnego dostawcy. Pokazał również wszystkie szablony, które zostały utworzone i edytowane przez dowolnego użytkownika, który pełnił tę samą rolę.

Możesz użyć przycisku **Nowy dokument** w obszarze roboczym **Zarządzanie dokumentami biznesowymi**, aby utworzyć i edytować szablon w formacie [sprawozdawczości elektronicznej (ER)](general-electronic-reporting.md) [konfiguracja](general-electronic-reporting.md#Configuration), który jest dostarczany przez innego dostawcę i znajduje się w bieżącej instancji Finance, lub aby przesłać nowy szablon z skoroszytu programu Excel. Dodatkowo w wersji 10.0.25 i nowszych możesz użyć przycisku **Nowy dokument**, aby utworzyć i edytować szablon w konfiguracji formatu ER, który jest przechowywany w [Globalnym repozytorium](general-electronic-reporting.md#Repository).

W przykładach w tym temacie aktywnym dostawcą jest Contoso i używasz go do stworzenia szablonu opartego na szablonie dostarczonym przez Microsoft. Szablon można również utworzyć, przesyłając własny szablon w formacie programu Excel.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWAVQg]

Film [Utwórz nowy dokument biznesowy za pomocą funkcji Zarządzanie dokumentami biznesowymi](https://youtu.be/gAIYl-mM_pw) (pokazany powyżej) jest dołączony do [Listy odtwarzania Finanse i Działania](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej na stronie YouTube.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Udostępnij interfejs użytkownika nowego dokumentu w zarządzaniu dokumentami biznesowymi

Aby rozpocząć korzystanie z interfejsu użytkownika nowego dokumentu w module Zarządzanie dokumentami biznesowymi, należy uruchomić funkcję **wyglądającą jak interfejs użytkownika Office do zarządzania dokumentami biznesowymi** w obszarze roboczym **Zarządzanie funkcjami**.

Aby włączyć tę funkcję dla wszystkich firm, należy wykonać następujące kroki.

1. W obszarze roboczym **Zarządzanie funkcjami** na karcie **Wszystkie** wybierz pozycję **Wyglądający jak Office interfejs użytkownika na potrzeby zarządzania dokumentami** biznesowymi na liście.
2. Wybierz opcję **Włącz teraz**, aby włączyć wybraną funkcję.
3. Odśwież stronę, aby uzyskać dostęp do nowej funkcji.

## <a name="add-or-activate-a-provider"></a>Dodaj lub aktywuj dostawcę

Każdy szablon dokumentu biznesowego jest przechowywany w konfiguracji struktury ER, która jest oznaczona jako należąca do określonego dostawcy konfiguracji. Kiedy tworzysz nowy szablon, tworzona jest nowa konfiguracja struktury ER, która go przechowuje. Dlatego dla tej konfiguracji musi być wskazany dostawca. Do tego celu wykorzystywany jest aktywny dostawca struktury ER. Jeśli w ER nie ma dostawcy, można go utworzyć. Jeśli nie ma *aktywnego* dostawcy, można aktywować jednego z istniejących dostawców. Okno dialogowe dodawania lub aktywacji dostawcy jest otwierane, gdy jest to konieczne, podczas gdy zaczynasz dodawać nowy szablon.

### <a name="add-a-new-provider"></a>Dodaj nowego dostawcę

Aby utworzyć nowego dostawcę, wykonaj następujące kroki w oknie dialogowym **Dostawca konfiguracji**:

1.  Na karcie **Wybierz dostawcę konfiguracji**, w polu **Nazwa** wprowadź nazwę nowego dostawcy.
2.  W polu **Adres internetowy** wpisz adres internetowy (URL) nowego dostawcy. 
3.  Kliknij przycisk **OK**.

    ![Tworzenie nowego dostawcy w Zarządzaniu dokumentami biznesowymi.](./media/bdm_create_provider.png)

Dodany dostawca zostanie uaktywniony automatycznie.

### <a name="activate-a-provider"></a>Aktywacja dostawcy

Aby aktywować nowego dostawcę, wykonaj następujące kroki w oknie dialogowym **Dostawca konfiguracji**:

1.  Na karcie **Wybierz dostawcę konfiguracji**, w polu **Dostawca konfiguracji** wybierz nazwę nowego dostawcy.
2.  Kliknij przycisk **OK**.

    ![Aktywowanie dostawcy w Zarządzaniu dokumentami biznesowymi.](./media/bdm_choose_provider.png)

Wybrany dostawca zostanie aktywowany.

> [!NOTE]
> Każdy szablon zarządzania dokumentami biznesowymi jest umieszczony w konfiguracji w formacie ER, która odnosi się do dostawcy jako autora konfiguracji. Dlatego dla każdego szablonu wymagany jest aktywny dostawca.

## <a name="edit-a-template-that-is-owned-by-another-provider"></a>Edytuj szablon, który jest własnością innego dostawcy

Ten przykład pokazuje, jak możesz użyć przycisku **Nowy dokument** w obszarze roboczym **Zarządzanie dokumentami biznesowymi**, aby utworzyć i edytować szablon w formacie konfiguracji sprawozdawczości elektronicznej (ER), który jest dostarczany przez innego dostawcę i znajduje się w bieżącej instancji Finance, lub aby przesłać nowy szablon z skoroszytu programu Excel. W tym przykładzie aktywnym dostawcą jest Contoso, który używa konfiguracji formatu ER dostarczonej przez Microsoft. Po wybraniu opcji **Nowy dokument** na karcie **Wybierz** na stronie **Utwórz nowy szablon** zostaną otwarte wszystkie szablony bieżącego wystąpienia finansowego, które należą do bieżącego dostawcy i innych dostawców. Wybierz szablon, aby go otworzyć. Możesz wtedy stworzyć nową, edytowalną kopię szablonu. Edytowany szablon zostanie następnie zapisany w nowej konfiguracji formatu, która jest generowana automatycznie.

1. W obszarze roboczym **Zarządzanie dokumentami biznesowymi** wybierz **Nowy dokument**.

    ![Strona obszaru roboczego zarządzania dokumentami biznesowymi.](./media/BDM_overview_new_template1.png)

2. Na stronie **Utwórz nowy szablon** na karcie **Wybierz** wybierz dokument, który ma być szablonem, a następnie wybierz pozycję **Utwórz dokument**.

    ![Dokumenty biznesowe, okno dialogowe.](./media/BDM_overview_new_template2.png)

3. W nowym oknie dialogowym, w polu **Tytuł**, zmień tytuł zgodnie z potrzebą. Tekst będzie używany do napełniania nowej nazwy tworzonej automatycznie konfiguracji formatu ER. Wersja robocza tej konfiguracji (**Raport o fakturach niezależnych dla odbiorców (GER) - Kopia**) będzie zawierać edytowany szablon i zostanie automatycznie oznaczona do uruchomienia tego formatu ER dla bieżącego użytkownika. Niezmodyfikowany oryginalny szablon z podstawowej konfiguracji formatu źródłowego będzie używany do uruchamiania tego formatu ER dla każdego innego użytkownika.
4. W polu **Nazwa** zmień nazwę pierwszej poprawki edytowalnego szablonu, który zostanie utworzony automatycznie.
5. W polu **Komentarz** zaktualizuj uwagę dla automatycznie wygenerowanej poprawki edytowalnego szablonu, która zostanie utworzona automatycznie.
6. Wybierz **OK**, aby potwierdzić rozpoczęcie procesu edycji.

    ![Tworzenie dokumentu, okno dialogowe.](./media/BDM_overview_new_template3.png)

## <a name="upload-a-template-that-uses-an-existing-excel-workbook"></a>Przekaż szablon, który używa istniejącego skoroszytu programu Excel

Ten przykład pokazuje, jak możesz użyć przycisku **Nowy dokument** w obszarze roboczym **Zarządzanie dokumentami biznesowymi**, aby utworzyć i edytować szablon w formacie konfiguracji sprawozdawczości elektronicznej (ER), w oparciu o dostępny szablon Excel. W tym przykładzie aktywny dostawca to Contoso i można użyć konfiguracji mapowania [modelu danych](er-overview-components.md#data-model-component) ER i [mapowania modelu](er-overview-components.md#model-mapping-component) ER dostarczanych przez Microsoft. Po wybraniu opcji **Nowy dokument** wybierz kartę **Prześlij** na stronie **Utwórz nowy szablon**. Tam możesz określić szczegóły przesyłania skoroszytu programu Excel. Po załadowaniu skoroszytu Excel jest on przekształcany w szablon dokumentu biznesowego, który jest otwarty do edycji. Edytowany szablon zostanie następnie zapisany w nowej konfiguracji formatu, która jest generowana automatycznie.

Przed przekazaniem szablonu należy podać wymagane informacje jak opisano w poniższych krokach.

1. W obszarze roboczym **Zarządzanie dokumentami biznesowymi** wybierz **Nowy dokument**.
2. Na stronie **Tworzenie nowego szablonu**, na karcie **Przekaż**, na karcie **Szablon** wybierz pozycję **Przeglądaj**, aby znaleźć i wybrać plik programu Excel, który ma być szablonem. W sekcji **Szablon** pola **Tytuł** i **Opis** są wypełniane automatycznie. Określają nazwę i opis nowej konfiguracji formatu ER, która jest tworzona automatycznie. Możesz edytować te pola według potrzeb.
3. W sekcji **Typ dokumentu**, w polu **Nazwa** określ typ dokumentu biznesowego. Ta wartość będzie używana do wyszukiwania poprawnego źródła danych (to znaczy konfiguracji modelu ER).

    ![Zakładka Szablon na karcie Prześlij na stronie Utwórz nowy szablon.](./media/BDM_overview_new_UI_import_21.jpg)

4. Na karcie **Źródło danych** na skróconej karcie **Filtruj** wybierz pozycję **Zastosuj filtr**. W sekcji **Źródło danych** pole **Nazwa** jest wypełniane automatycznie lub można ręcznie wybrać wartość. Filtr umożliwia wyszukiwanie odpowiedniej nazwy źródła danych według nazwy, opisu, kodu kraju/regionu i typu dokumentu biznesowego.

    ![Zakładka Źródło danych na karcie Prześlij na stronie Utwórz nowy szablon.](./media/BDM_overview_new_UI_import_31.jpg)

    > [!NOTE]
    > Skrócona karta **Filtruj** będzie używana do wyszukiwania poprawnego źródła danych (to znaczy konfiguracji modelu ER). Możesz edytować wszystkie pola filtrów, aby znaleźć najbardziej odpowiednie źródło danych dla przesyłanego dokumentu.
    > 
    > Warunki na skróconej karcie **Filtruj** są używane jako warunki **OR**.

5. Na karcie **mapowanie** wybierz opcję **Automatyczne wykrywanie**. Pole **Definicja źródłowa** jest wypełniane automatycznie lub można ręcznie wybrać wartość. Na tej karcie jest przedstawiane końcowe mapowanie elementów z szablonu i modelu.

    ![Zakładka Mapowanie na karcie Prześlij na stronie Utwórz nowy szablon.](./media/BDM_overview_new_UI_import_41.jpg)

    > [!NOTE]
    > Mapowanie w sekcji **Struktura szablonu** korzysta z pełnego dopasowania etykiet lub opisów w źródle danych w języku użytkownika i w nazwie komórki w szablonie.

6. Wybierz pozycję **Utwórz dokument**, aby potwierdzić, że chcesz utworzyć szablon i rozpocząć proces edycji.

Aby uzyskać więcej informacji, zajrzyj do omówienia [Zarządzania dokumentami biznesowymi](er-business-document-management.md).

## <a name="upload-a-template-from-the-global-repository"></a>Wgrywanie szablonu z Globalnego repozytorium

Ten przykład pokazuje, jak możesz użyć przycisku **Nowy dokument** w obszarze roboczym **Zarządzanie dokumentami biznesowymi**, aby utworzyć i edytować szablon w formacie konfiguracji sprawozdawczości elektronicznej (ER), podany przez Microsoft i zlokalizowanym w repozytorium globalnym. W tym przykładzie aktywnym dostawcą jest Contoso, który używa konfiguracji formatu ER dostarczonej przez Microsoft. Po wybraniu **Nowego dokumentu**, zakładka **Import z repozytorium globalnego** na stronie **Utwórz nowy szablon** pokazuje wszystkie szablony dokumentów biznesowych, które są przechowywane w repozytorium globalnym, ale brakuje ich w bieżącej instancji Finance. Gdy wybierzesz szablon, zostanie on zaimportowany z globalnego repozytorium do bieżącej instancji Finance, aby stworzyć nową, edytowalną kopię. Edytowany szablon zostanie następnie zapisany w nowej konfiguracji formatu, która jest generowana automatycznie.

1. W obszarze roboczym **Zarządzanie dokumentami biznesowymi** wybierz **Nowy dokument**.
2. Na stronie **Utwórz nowy szablon** na karcie **Import z globalnego repozytorium** wybierz dokument, który ma być szablonem, a następnie wybierz pozycję **Utwórz dokument**.

    ![Zakładka Import z Globalnego repozytorium na stronie Utwórz nowy szablon.](./media/BDM_overview_new_template22.png)

3. W polu komunikatu wybierz opcję **Tak**, aby potwierdzić, że chcesz zaimportować wybrany dokument z repozytorium globalnym do bieżącego wystąpienia finansowego. Jeśli zostanie wyświetlony monit o autoryzację, postępuj zgodnie z instrukcjami wyświetlanymi na ekranie.
4. W nowym oknie dialogowym, w polu **Tytuł**, zmień tytuł zgodnie z potrzebą. Tekst będzie używany do napełniania nowej nazwy tworzonej automatycznie konfiguracji formatu ER. Wersja robocza tej konfiguracji (**Notatka z listu zbiorczego (Excel) - Kopia**) będzie zawierać edytowany szablon i zostanie automatycznie oznaczona do uruchomienia tego formatu ER dla bieżącego użytkownika. Niezmodyfikowany oryginalny szablon z podstawowej konfiguracji formatu źródłowego będzie używany do uruchamiania tego formatu ER dla każdego innego użytkownika.
5. W polu **Nazwa** zmień nazwę pierwszej poprawki edytowalnego szablonu, który zostanie utworzony automatycznie.
6. W polu **Komentarz** zaktualizuj uwagę dla automatycznie wygenerowanej poprawki edytowalnego szablonu, która zostanie utworzona automatycznie.
7. Wybierz **OK**, aby potwierdzić rozpoczęcie procesu edycji.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
