---
title: Nowy interfejs użytkownika w stylu Microsoft Office dokumentu w zarządzaniu dokumentami biznesowymi
description: W tym temacie wyjaśniono, jak używać nowego interfejsu użytkownika w funkcji zarządzania dokumentami biznesowymi struktury raportowania elektronicznego (ER).
author: v-anamir
ms.date: 04/12/2021
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
ms.openlocfilehash: e8a3782e5beb7d16accc0a56447d5db1f1376dd8
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6350191"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Nowy interfejs użytkownika w stylu Microsoft Office dokumentu w zarządzaniu dokumentami biznesowymi

[!include [banner](../includes/banner.md)]

Zarządzanie dokumentami biznesowymi pozwala użytkownikom korzystać z usługi Microsoft 365 lub odpowiedniej aplikacji komputerowej Microsoft Office. Edycja może obejmować zmiany projektu lub nowe wdrożenia albo użytkownicy mogą dodawać symbole zastępcze w celu dołączenia dodatkowych danych bez konieczności zmieniania kodu źródłowego. Aby uzyskać więcej informacji na temat pracy z zarządzaniem dokumentami biznesowymi, zapoznaj się z [Omówieniem zarządzania dokumentami biznesowymi](er-business-document-management.md).

Nowy interfejs użytkownika (UI) jest wyraźniejszy i wygodniejszy do używania. W obszarze **Dokument biznesowy** są wyświetlane tylko szablony dostępne dla bieżącego dostawcy. W poprzednim interfejsie użytkownika na karcie **Szablon** zostały wyświetlone wszystkie szablony dostępne dla dowolnego dostawcy. Pokazał również wszystkie szablony, które zostały utworzone i edytowane przez dowolnego użytkownika, który pełnił tę samą rolę.

Można użyć przycisku **Nowy dokument** , który umożliwia użytkownikom tworzenie i edytowanie szablonu w konfiguracji formatu sprawozdawczości elektronicznej (ER) dostarczonej przez innego dostawcę. W przykładzie przedstawionym w tym temacie dostawcą jest Microsoft. Szablon można również utworzyć, przesyłając własny szablon w formacie programu Excel.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWAVQg]

Film [Utwórz nowy dokument biznesowy za pomocą funkcji Zarządzanie dokumentami biznesowymi](https://youtu.be/gAIYl-mM_pw) (pokazany powyżej) jest dołączony do [Listy odtwarzania Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej na stronie YouTube.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Udostępnij interfejs użytkownika nowego dokumentu w zarządzaniu dokumentami biznesowymi

Aby rozpocząć korzystanie z interfejsu użytkownika nowego dokumentu w module Zarządzanie dokumentami biznesowymi, należy uruchomić funkcję **wyglądającą jak interfejs użytkownika Office do zarządzania dokumentami biznesowymi** w obszarze roboczym **Zarządzanie funkcjami**.

Aby włączyć tę funkcję dla wszystkich firm, należy wykonać następujące kroki.

1. W obszarze roboczym **Zarządzanie funkcjami** na karcie **Wszystkie** wybierz pozycję **Wyglądający jak Office interfejs użytkownika na potrzeby zarządzania dokumentami** biznesowymi na liście.
2. Wybierz opcję **Włącz teraz**, aby włączyć wybraną funkcję.
3. Odśwież stronę, aby uzyskać dostęp do nowej funkcji.

## <a name="edit-templates-that-are-owned-by-other-providers"></a>Edytuj szablony należące do innych dostawców

1. W obszarze roboczym **Zarządzanie dokumentami biznesowymi** wybierz **Nowy dokument**.

    ![Strona obszaru roboczego zarządzania dokumentami biznesowymi.](./media/BDM_overview_new_template1.png)

2. Na karcie **Wybierz** wybierz dokument, który ma być używany jako szablon, a następnie wybierz opcję **Utwórz dokument**.

    ![Dokumenty biznesowe, okno dialogowe.](./media/BDM_overview_new_template2.png)

3. W nowym oknie dialogowym, w polu **Tytuł**, zmień tytuł zgodnie z potrzebą. Tekst będzie używany do napełniania nowej nazwy tworzonej automatycznie konfiguracji formatu ER. Wersja robocza tej konfiguracji (**Raport o fakturach niezależnych dla odbiorców (GER) - Kopia**) będzie zawierać edytowany szablon i zostanie automatycznie oznaczona do uruchomienia tego formatu ER dla bieżącego użytkownika. Niezmodyfikowany oryginalny szablon z podstawowej konfiguracji formatu źródłowego będzie używany do uruchamiania tego formatu ER dla każdego innego użytkownika.
4. W polu **Nazwa** zmień nazwę pierwszej poprawki edytowalnego szablonu, który zostanie utworzony automatycznie.
5. W polu **Komentarz** zaktualizuj uwagę dla automatycznie wygenerowanej poprawki edytowalnego szablonu, która zostanie utworzona automatycznie.
6. Wybierz **OK**, aby potwierdzić rozpoczęcie procesu edycji.

    ![Tworzenie dokumentu, okno dialogowe.](./media/BDM_overview_new_template3.png)

Przycisk **Nowy dokument** umożliwia użytkownikom tworzenie i edytowanie szablonu w konfiguracji formatu sprawozdawczości elektronicznej (ER) dostarczonej przez innego dostawcę. W przykładzie przedstawionym w tym temacie dostawcą jest Microsoft. Kliknięcie przycisku **Nowy dokument** powoduje wyświetlenie wszystkich szablonów należących do bieżącego i innych dostawców. Po wybraniu szablonu, zostanie on otwarty do edycji. Edytowany szablon zostanie następnie zapisany w nowej konfiguracji formatu, która jest generowana automatycznie.

## <a name="upload-a-template-that-uses-an-existing-excel-format"></a>Przekaż szablon, który używa istniejącego formatu programu Excel
Przed przekazaniem szablonu należy podać wymagane informacje jak opisano w poniższych krokach.

1. W obszarze roboczym **Zarządzanie dokumentami biznesowymi** wybierz **Nowy dokument**.

    ![Strona obszaru roboczego zarządzania dokumentami biznesowymi.](./media/BDM_overview_new_template1.png)
    
2. Na stronie **Tworzenie nowego szablonu**, na karcie **Przekaż**, na karcie **Szablon** wybierz pozycję **Przeglądaj**, aby znaleźć i wybrać plik programu Excel, który ma być szablonem. W sekcji **Szablon** pola **Tytuł** i **Opis** są wypełniane automatycznie. Określają nazwę i opis nowej konfiguracji formatu ER, która jest tworzona automatycznie. Możesz edytować te pola według potrzeb.
3. W sekcji **Typ dokumentu**, w polu **Nazwa** określ typ dokumentu biznesowego. Ta wartość będzie używana do wyszukiwania poprawnego źródła danych (to znaczy konfiguracji modelu ER).

    ![Karta szablonu.](./media/BDM_overview_new_UI_import_21.jpg)

4. Na karcie **Źródło danych** na skróconej karcie **Filtruj** wybierz pozycję **Zastosuj filtr**. W sekcji **Źródło danych** pole **Nazwa** jest wypełniane automatycznie lub można ręcznie wybrać wartość. Filtr umożliwia wyszukiwanie odpowiedniej nazwy źródła danych według nazwy, opisu, kodu kraju/regionu i typu dokumentu biznesowego.

    ![Karta Źródło danych.](./media/BDM_overview_new_UI_import_31.jpg)
    
    > [!NOTE]
    > Skrócona karta **Filtruj** będzie używana do wyszukiwania poprawnego źródła danych (to znaczy konfiguracji modelu ER). Możesz edytować wszystkie pola filtrów, aby znaleźć najbardziej odpowiednie źródło danych dla przesyłanego dokumentu.
    > 
    > Warunki na skróconej karcie **Filtruj** są używane jako warunki **OR**.
    
5. Na karcie **mapowanie** wybierz opcję **Automatyczne wykrywanie**. Pole **Definicja źródłowa** jest wypełniane automatycznie lub można ręcznie wybrać wartość. Na tej karcie jest przedstawiane końcowe mapowanie elementów z szablonu i modelu.

    ![Karta Mapowanie.](./media/BDM_overview_new_UI_import_41.jpg)
    
   > [!NOTE]
   > Mapowanie w sekcji **Struktura szablonu** korzysta z pełnego dopasowania etykiet lub opisów w źródle danych w języku użytkownika i w nazwie komórki w szablonie.

6. Wybierz pozycję **Utwórz dokument**, aby potwierdzić, że chcesz utworzyć szablon i rozpocząć proces edycji.

Aby uzyskać więcej informacji, zajrzyj do omówienia [Zarządzania dokumentami biznesowymi](er-business-document-management.md).

Jeśli w raportowaniu elektronicznym nie ma dostawcy, można go utworzyć. Jeśli nie ma aktywnego dostawcy, możesz go aktywować.

- Aby utworzyć dostawcę, zmień nazwę dostawcy w polu **Nazwa**, zaktualizuj adres internetowy nowego dostawcy w polu **Adresu internetowego** i wybierz przycisk **OK**, aby potwierdzić.

    ![Utwórz nowego dostawcę w BDM.](./media/bdm_create_provider.png)
    
- Aby uaktywnić istniejącego dostawcę, wybierz nazwę dostawcy w polu **Dostawca konfiguracji** i wybierz przycisk **OK**, aby ustawić dostawcę jako aktywnego.

    ![Aktywuj dostawcę w BDM.](./media/bdm_choose_provider.png)

> [!NOTE]
> Każdy szablon BDM odnosi się do dostawcy jako autora konfiguracji. Z tego względu dla szablonu jest wymagany aktywny dostawca.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
