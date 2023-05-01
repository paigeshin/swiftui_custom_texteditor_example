# swiftui_custom_texteditor_example

```swift
    TextEditor(text: self.$memo)
            .placeholder(when: self.memo.isEmpty, placeholder: {
                VStack {
                    Text(R.String.enterMemo)
                        .fontWeight(.regular)
                        .foregroundColor(self.theme.backgroundColor.fontColor.opacity(0.5))
                        .padding(.top, 7)
                        .padding(.leading, 4)
                    
                    Spacer()
                }
            })
            .focused(self.$memoFocused)
            .frame(maxHeight: 86)
            .autocorrectionDisabled(true)
            .textInputAutocapitalization(.never)
            .padding(EdgeInsets(top: 6, leading: 12, bottom: 6, trailing: 12))
            .foregroundColor(self.theme.backgroundColor.fontColor)
            .adaptiveFontSize(customFont: self.font, 16)
            .cornerRadius(16)
            .overlay {
                RoundedRectangle(cornerRadius: 12)
                    .stroke(self.memoFocused || !self.memo.isEmpty ? self.theme.primaryColor : self.theme.primaryColor.opacity(0.5), lineWidth: 2)
            }
            .preferredColorScheme(self.theme.scheme)
            .onChange(of: self.title) { newValue in
                Log.info("title changed => \(newValue)")
            }
            .onChange(of: self.protein) { newValue in
                Log.info("protein chagned => \(newValue)")
            }
            
            
```

```swift
if #available(iOS 16.0, *) {
    CustomTextEditor()
        .scrollContentBackground(.hidden)
} else {
    CustomTextEditor()
}
```
