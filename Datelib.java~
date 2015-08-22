import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.TimeZone;

/**
 * Converts UTC time to local time, vice-versa and everything in between
 */
public class Datelib {
    public static String getCurrentDateTimeinLocalTime(){
        Date date = new Date();
        return niftyFunctions.pollenDateFormat.format(date);
    }

    public static String converDateTime(Date date){
        String output;
        try{
            output = niftyFunctions.pollenDateFormat.format(date);
        }catch (Exception e){
            output = "Error in time: Datelib";
            e.printStackTrace();
        }
        return output;
    }

    public static String getCurrentDateTimeinUTC(){
        Date date = new Date();
        SimpleDateFormat format = new SimpleDateFormat("yyyy-MM-dd hh:mm:ssZ");
        format.setTimeZone(TimeZone.getTimeZone("UTC"));
        return format.format(date);
    }

    public static String getCurrentDateTimeinUTC(Date date){
        SimpleDateFormat format = new SimpleDateFormat("yyyy-MM-dd hh:mm:ssZ");
        format.setTimeZone(TimeZone.getTimeZone("UTC"));
        return format.format(date);
    }

    /**
     * Converts server UTC date in form ("YYYY-MM-DD HH:MM:SS") to UTC string in form ("YYYY-MM-DD HH:MM:SS+0000")
     *
     * @param date
     * @return
     */
    public static String convertServerUTCDateToDBUTC(String date){
        String output;

        SimpleDateFormat dateFormatUTC = new SimpleDateFormat(
                "yyyy-MM-dd hh:mm:ss");
        SimpleDateFormat dateFormatUTCtoDB = new SimpleDateFormat(
                "yyyy-MM-dd hh:mm:ssZ");
        dateFormatUTC.setTimeZone(TimeZone.getTimeZone("UTC"));
        dateFormatUTCtoDB.setTimeZone(TimeZone.getTimeZone("UTC"));

        try{
            output = dateFormatUTCtoDB.format(dateFormatUTC.parse(date));
        }catch (ParseException e){
            // do nothing
            output = date;
        }

        return output;
    }

    public static Date getLocalDatefromUTC(String date){
        Date output;
        try{
            output = niftyFunctions.pollenDateFormat.parse(date);
        }catch (Exception e){
            e.printStackTrace();
            output = new Date();
        }

        return output;
    }
}

