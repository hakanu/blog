---
layout: post
title: Some handy Android code snippets
date: '2014-10-15 23:18:08'
---

[![](http://distilleryimage4.ak.instagram.com/6d2edcfeefc411e1a9d522000a1cd9f8_7.jpg)](http://instagram.com/uhakan)

## Email Validation

`public static boolean validateEmail(String email) {
        return android.util.Patterns.EMAIL_ADDRESS.matcher(email).matches();
}`

## Share Button

`Intent sharingIntent = new Intent(android.content.Intent.ACTION_SEND);
sharingIntent.setType("text/plain");
Resources res = activity.getResources();
String shareSubject = res.getString(R.string.share_subject);
String shareVia = res.getString(R.string.share_via);
String shareBody = res.getString(R.string.share_body) + shareAdditional;
sharingIntent.putExtra(android.content.Intent.EXTRA_SUBJECT, shareSubject);
sharingIntent.putExtra(android.content.Intent.EXTRA_TEXT, shareBody); 
activity.startActivity(Intent.createChooser(sharingIntent, shareVia));`

## Show Simple Popup - AlertDialog
`private void showPopup() {
        AlertDialog alertDialog = new AlertDialog.Builder(getActivity()).create();
        alertDialog.setTitle("Title");
        alertDialog.setMessage("Message");
        alertDialog.setButton("OK", new DialogInterface.OnClickListener() {
            public void onClick(DialogInterface dialog, int which) {
                if(MainActivity.DEBUG) {
                    System.out.println("ok clicked");
                }
            }
        });
        // Set the Icon for the Dialog
        alertDialog.setIcon(R.drawable.ic_launcher);
        alertDialog.show();
}`

## Create a Java Set
`Set<Integer> numbers = new TreeSet<Integer>();`

## Get string from string array values
`String[] mTestArray =   getResources().getStringArray(R.array.planets_array);`

## Make custom listview items clickable
In the custom item xml add this to the master layout:
`android:descendantFocusability="blocksDescendants"`

## Read/Write from SharedPreferences
`private SharedPreferences getSharedPreferenceHandle() {
    if (MainActivity.DEBUG) {
        System.out.println("getting shared pref handle");
    }

    SharedPreferences sharedPref = getActivity().getSharedPreferences(
            getString(R.string.my_brands_preference_file_key), Context.MODE_PRIVATE);
    return sharedPref;
}

private void writeToSharedPreferences(String key, ArrayList<String> values) {
    if (MainActivity.DEBUG) {
        System.out.println("writing to shared pref: " + values);
    }

    Set<String> setValues = new TreeSet<String>();
    for (String s: values) {
        setValues.add(s);
    }
    SharedPreferences sharedPref = getSharedPreferenceHandle();
    SharedPreferences.Editor editor = sharedPref.edit();
    editor.putStringSet(key, setValues);
    editor.commit();
}`

## Change SDK path of Android Studio
File->project Structure into Project StructureLeft > SDKsPress +, add another sdk

## Transparent Button Background
`?android:attr/selectableItemBackground`

## Read from a file
`private String readFromFile(String path) {
    String ret = "";

    try {
        InputStream inputStream = openFileInput(path);

        if ( inputStream != null ) {
            InputStreamReader inputStreamReader = new InputStreamReader(inputStream);
            BufferedReader bufferedReader = new BufferedReader(inputStreamReader);
            String receiveString = "";
            StringBuilder stringBuilder = new StringBuilder();

            while ( (receiveString = bufferedReader.readLine()) != null ) {
                stringBuilder.append(receiveString);
            }
            inputStream.close();
            ret = stringBuilder.toString();
        }
    }
    catch (FileNotFoundException e) {
        Log.e("login activity", "File not found: " + e.toString());
    } catch (IOException e) {
        Log.e("login activity", "Can not read file: " + e.toString());
    }

    return ret;
}`

## Write to a file with private mode
`private void writeToFile(String filePath, String data) {
    try {
        OutputStreamWriter outputStreamWriter = new OutputStreamWriter(openFileOutput(
                filePath, Context.MODE_PRIVATE));
        outputStreamWriter.write(data);
        outputStreamWriter.close();
    }
    catch (IOException e) {
        Log.e("Exception", "File write failed: " + e.toString());
    }
}`

## Hide action bar
`getActionBar().hide();`
