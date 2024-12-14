# PL3-Project
    // Delete word event
    deleteButton.Click.Add(fun _ ->
        let word = wordTextBox.Text.Trim().ToLower()
        if dictionary.ContainsKey(word) then
            dictionary <- dictionary.Remove(word)
            MessageBox.Show(sprintf "'%s' deleted successfully!" word) |> ignore
            saveDictionaryToFile(dictionaryFilePath)
        else
            MessageBox.Show(sprintf "'%s' does not exist in the dictionary." word) |> ignore
    )
