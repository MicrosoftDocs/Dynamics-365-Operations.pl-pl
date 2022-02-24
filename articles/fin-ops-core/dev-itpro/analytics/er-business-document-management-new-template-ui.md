---
title: Nowy interfejs użytkownika dokumentu w zarządzaniu dokumentami biznesowymi
description: Ten temat zawiera informacje dotyczące korzystania z interfejsu użytkownika nowego dokumentu (UI) w funkcji zarządzania dokumentami biznesowymi struktury modułu raportowanie elektroniczne (ER).
author: v-anamir
manager: AnnBe
ms.date: 05/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 2cb6e0da4af07b9b8486bf1e5bda29523cbd08e9
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681359"
---
# <a name="new-document-user-interface-in-business-document-management"></a>Nowy interfejs użytkownika dokumentu w zarządzaniu dokumentami biznesowymi

[!include [banner](../includes/banner.md)]

Zarządzanie dokumentami biznesowymi pozwala użytkownikom korzystać z usługi Microsoft 365 lub odpowiedniej aplikacji komputerowej Microsoft Office. Edycja może obejmować zmiany projektu lub nowe wdrożenia albo użytkownicy mogą dodawać symbole zastępcze w celu dołączenia dodatkowych danych bez konieczności zmieniania kodu źródłowego. Aby uzyskać więcej informacji na temat pracy z zarządzaniem dokumentami biznesowymi, zapoznaj się z [Omówieniem zarządzania dokumentami biznesowymi](er-business-document-management.md).

Nowy interfejs użytkownika (UI) nowego dokumentu jest wyraźniejszy i wygodniejszy do używania. W obszarze **Dokument biznesowy** są wyświetlane tylko szablony dostępne dla bieżącego dostawcy.

Przycisk **Nowy dokument** umożliwia użytkownikom tworzenie i edytowanie szablonu w konfiguracji formatu sprawozdawczości elektronicznej (ER) dostarczonej przez innego dostawcę. W przykładzie przedstawionym w tym temacie dostawcą jest Microsoft.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Udostępnij interfejs użytkownika nowego dokumentu w zarządzaniu dokumentami biznesowymi

Aby rozpocząć korzystanie z interfejsu użytkownika nowego dokumentu w module Zarządzanie dokumentami biznesowymi, należy uruchomić funkcję **wyglądającą jak interfejs użytkownika Office do zarządzania dokumentami biznesowymi** w obszarze roboczym **Zarządzanie funkcjami**.

Aby włączyć tę funkcję dla wszystkich firm, należy wykonać następujące kroki.

1. W obszarze roboczym **Zarządzanie funkcjami** na karcie **Nowy** wybierz pozycję **Wyglądający jak Office interfejs użytkownika na potrzeby zarządzania dokumentami** biznesowymi na liście.
2. Wybierz opcję **Włącz teraz**, aby włączyć wybraną funkcję.
3. Odśwież stronę, aby uzyskać dostęp do nowej funkcji.

### <a name="edit-templates-that-are-owned-by-other-providers"></a>Edytuj szablony należące do innych dostawców

1. W obszarze roboczym **Zarządzanie dokumentami biznesowymi** wybierz **Nowy dokument**.

    ![Strona obszaru roboczego zarządzania dokumentami biznesowymi](./media/BDM_overview_new_template1.png)

2. W oknie dialogowym wybierz dokument, który ma być używany jako szablon, a następnie wybierz opcję **Utwórz dokument**.

    ![Dokumenty biznesowe, okno dialogowe](./media/BDM_overview_new_template2.png)

3. W nowym oknie dialogowym, w polu **Tytuł**, zmień tytuł zgodnie z potrzebą. Tekst będzie używany do napełniania nowej nazwy tworzonej automatycznie konfiguracji formatu ER. Wersja robocza tej konfiguracji (**Raport o fakturach niezależnych dla odbiorców (GER) - Kopia**) będzie zawierać edytowany szablon i zostanie automatycznie oznaczona do uruchomienia tego formatu ER dla bieżącego użytkownika. Niezmodyfikowany oryginalny szablon z podstawowej konfiguracji formatu źródłowego będzie używany do uruchamiania tego formatu ER dla każdego innego użytkownika.
4. W polu **Nazwa** zmień nazwę pierwszej poprawki edytowalnego szablonu, który zostanie utworzony automatycznie.
5. W polu **Komentarz** zaktualizuj uwagę dla automatycznie wygenerowanej poprawki edytowalnego szablonu, która zostanie utworzona automatycznie.
6. Wybierz **OK**, aby potwierdzić rozpoczęcie procesu edycji.

    ![Tworzenie dokumentu, okno dialogowe](./media/BDM_overview_new_template3.png)

Przycisk **Nowy dokument** umożliwia użytkownikom tworzenie i edytowanie szablonu w konfiguracji formatu sprawozdawczości elektronicznej (ER) dostarczonej przez innego dostawcę. W przykładzie przedstawionym w tym temacie dostawcą jest Microsoft. Kliknięcie przycisku **Nowy dokument** powoduje wyświetlenie wszystkich szablonów należących do bieżącego i innych dostawców. Po wybraniu szablonu, zostanie on otwarty do edycji. Edytowany szablon zostanie następnie zapisany w nowej konfiguracji formatu, która jest generowana automatycznie.

Aby uzyskać więcej informacji, zajrzyj do omówienia [Zarządzania dokumentami biznesowymi](er-business-document-management.md).
